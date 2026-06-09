# STRW::PathAppendW(ushort const *)

- ea: `0x1800120c8`
- end: `0x180012162`
- name: `?PathAppendW@STRW@@QEAAJPEBG@Z`
- size: `154`
- prototype: `__int64 __fastcall(STRW *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a220`

## callees

- `0x180004640`
- `0x180009578`
- `0x1800120c8`
- `0x180012f8e`
- `0x180012fc0`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x180012114`
- `SHLWAPI!PathAppendW` at `0x180012114`

## pseudocode

```c
__int64 __fastcall STRW::PathAppendW(STRW *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // r8
  __int64 result; // rax
  const WCHAR *v5; // r11
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = &ExistingFileName;
  if ( *(_DWORD *)this )
    v2 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  result = StringCchCopyW(pszPath, 0x104u, v2);
  if ( (int)result >= 0 )
  {
    if ( PathAppendW(pszPath, v5) )
    {
      memset_0(*((void **)this + 1), 0, 2LL * *(unsigned int *)this);
      *(_DWORD *)this = 0;
      return STRW::Append(this, pszPath);
    }
    else
    {
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800120c8  push    rbx
0x1800120ca  sub     rsp, 240h
0x1800120d1  mov     rax, cs:__security_cookie
0x1800120d8  xor     rax, rsp
0x1800120db  mov     [rsp+248h+var_18], rax
0x1800120e3  cmp     dword ptr [rcx], 0
0x1800120e6  lea     r8, ExistingFileName
0x1800120ed  mov     r11, rdx
0x1800120f0  mov     rbx, rcx
0x1800120f3  jz      short loc_1800120F9
0x1800120f5  mov     r8, [rcx+8]; unsigned __int16 *
0x1800120f9  mov     edx, 104h; unsigned __int64
0x1800120fe  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x180012103  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012108  test    eax, eax
0x18001210a  js      short loc_180012149
0x18001210c  mov     rdx, r11; pszMore
0x18001210f  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180012114  call    cs:__imp_PathAppendW
0x18001211a  test    eax, eax
0x18001211c  jz      short loc_180012144
0x18001211e  mov     r8d, [rbx]
0x180012121  xor     edx, edx; Val
0x180012123  mov     rcx, [rbx+8]; void *
0x180012127  add     r8, r8; Size
0x18001212a  call    memset_0
0x18001212f  lea     rdx, [rsp+248h+pszPath]; unsigned __int16 *
0x180012134  mov     dword ptr [rbx], 0
0x18001213a  mov     rcx, rbx; this
0x18001213d  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180012142  jmp     short loc_180012149
0x180012144  mov     eax, 80004005h
0x180012149  mov     rcx, [rsp+248h+var_18]
0x180012151  xor     rcx, rsp; StackCookie
0x180012154  call    __security_check_cookie
0x180012159  add     rsp, 240h
0x180012160  pop     rbx
0x180012161  retn
```
