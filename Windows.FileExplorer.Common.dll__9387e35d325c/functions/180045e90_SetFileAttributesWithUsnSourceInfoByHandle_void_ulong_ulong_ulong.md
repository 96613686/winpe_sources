# SetFileAttributesWithUsnSourceInfoByHandle(void *,ulong,ulong,ulong)

- ea: `0x180045e90`
- end: `0x180045f66`
- name: `?SetFileAttributesWithUsnSourceInfoByHandle@@YAJPEAXKKK@Z`
- size: `214`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180045e00`
- `0x180046300`

## callees

- `0x18000c668`
- `0x180037780`
- `0x180045e90`
- `0x180046588`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180045f3a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180045f3a`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180045ed5`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180045ed5`

## pseudocode

```c
__int64 __fastcall SetFileAttributesWithUsnSourceInfoByHandle(void *a1, int a2, int a3, unsigned int a4)
{
  __int64 result; // rax
  __m128i si128; // [rsp+20h] [rbp-88h] BYREF
  __int64 v10; // [rsp+30h] [rbp-78h]
  __int64 v11; // [rsp+38h] [rbp-70h]
  int v12; // [rsp+40h] [rbp-68h]
  int v13; // [rsp+44h] [rbp-64h]
  _OWORD FileInformation[2]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v15; // [rsp+68h] [rbp-40h]

  v15 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( GetFileInformationByHandleEx(a1, FileBasicInfo, FileInformation, 0x28u)
    || (result = ResultFromKnownLastError(), (int)result >= 0) )
  {
    v11 = -1;
    v10 = -1;
    v13 = 0;
    v12 = a2 & a3 | v15 & ~a3;
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    result = SetUsnSourceInfo(a1, a4);
    if ( (int)result >= 0 )
    {
      if ( SetFileInformationByHandle(a1, FileBasicInfo, &si128, 0x28u) )
        return 0;
      else
        return ResultFromKnownLastError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x180045e90  push    rbx
0x180045e92  push    rbp
0x180045e93  push    rsi
0x180045e94  push    rdi
0x180045e95  sub     rsp, 88h
0x180045e9c  mov     rax, cs:__security_cookie
0x180045ea3  xor     rax, rsp
0x180045ea6  mov     [rsp+0A8h+var_38], rax
0x180045eab  xor     eax, eax
0x180045ead  xorps   xmm0, xmm0
0x180045eb0  mov     ebp, r9d
0x180045eb3  mov     [rsp+0A8h+var_40], rax
0x180045eb8  mov     ebx, r8d
0x180045ebb  mov     esi, edx
0x180045ebd  lea     r8, [rsp+0A8h+FileInformation]; lpFileInformation
0x180045ec2  xor     edx, edx; FileInformationClass
0x180045ec4  lea     r9d, [rax+28h]; dwBufferSize
0x180045ec8  mov     rdi, rcx
0x180045ecb  movups  [rsp+0A8h+FileInformation], xmm0
0x180045ed0  movups  [rsp+0A8h+var_50], xmm0
0x180045ed5  call    cs:__imp_GetFileInformationByHandleEx
0x180045edb  test    eax, eax
0x180045edd  jnz     short loc_180045EE8
0x180045edf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180045ee4  test    eax, eax
0x180045ee6  js      short loc_180045F4D
0x180045ee8  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180045ef0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180045ef4  mov     [rsp+0A8h+var_70], rax
0x180045ef9  mov     edx, ebp; unsigned int
0x180045efb  mov     [rsp+0A8h+var_78], rax
0x180045f00  mov     rcx, rdi; void *
0x180045f03  mov     eax, ebx
0x180045f05  mov     [rsp+0A8h+var_64], 0
0x180045f0d  not     eax
0x180045f0f  and     ebx, esi
0x180045f11  and     eax, dword ptr [rsp+0A8h+var_40]
0x180045f15  or      eax, ebx
0x180045f17  mov     [rsp+0A8h+var_68], eax
0x180045f1b  movdqu  [rsp+0A8h+var_88], xmm0
0x180045f21  call    ?SetUsnSourceInfo@@YAJPEAXK@Z; SetUsnSourceInfo(void *,ulong)
0x180045f26  test    eax, eax
0x180045f28  js      short loc_180045F4D
0x180045f2a  mov     r9d, 28h ; '('; dwBufferSize
0x180045f30  lea     r8, [rsp+0A8h+var_88]; lpFileInformation
0x180045f35  xor     edx, edx; FileInformationClass
0x180045f37  mov     rcx, rdi; hFile
0x180045f3a  call    cs:__imp_SetFileInformationByHandle
0x180045f40  test    eax, eax
0x180045f42  jz      short loc_180045F48
0x180045f44  xor     eax, eax
0x180045f46  jmp     short loc_180045F4D
0x180045f48  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180045f4d  mov     rcx, [rsp+0A8h+var_38]
0x180045f52  xor     rcx, rsp; StackCookie
0x180045f55  call    __security_check_cookie
0x180045f5a  add     rsp, 88h
0x180045f61  pop     rdi
0x180045f62  pop     rsi
0x180045f63  pop     rbp
0x180045f64  pop     rbx
0x180045f65  retn
```
