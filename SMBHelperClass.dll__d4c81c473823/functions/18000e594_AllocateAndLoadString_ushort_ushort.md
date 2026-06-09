# AllocateAndLoadString(ushort * *,ushort *)

- ea: `0x18000e594`
- end: `0x18000e69f`
- name: `?AllocateAndLoadString@@YAXPEAPEAGPEAG@Z`
- size: `267`
- prototype: `void(unsigned __int16 **, unsigned __int16 *)`
- caller_count: `9`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a690`
- `0x18000ab58`
- `0x18000c4b0`
- `0x18000c550`
- `0x18000c854`
- `0x18000dda4`
- `0x18000f684`
- `0x18000f970`
- `0x18000fa20`

## callees

- `0x18000257c`
- `0x18000a320`
- `0x18000e594`
- `0x18000eddc`
- `0x18000ee10`
- `0x18000fc30`

## import_xrefs

- `USER32!LoadStringW` at `0x18000e5db`
- `USER32!LoadStringW` at `0x18000e5db`

## pseudocode

```c
void __fastcall AllocateAndLoadString(unsigned __int16 **a1, unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rdi
  unsigned __int64 v4; // rbx
  unsigned __int16 *TestMemory; // rax
  void *v6; // r11
  _DWORD pExceptionObject[4]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR Buffer[512]; // [rsp+30h] [rbp-428h] BYREF

  v2 = a2;
  if ( (unsigned __int64)a2 < 0x10000 )
  {
    if ( LoadStringW(off_18001B080, (unsigned __int16)a2, Buffer, 512) < 0 )
    {
      pExceptionObject[0] = 4;
      throw (TestException *)pExceptionObject;
    }
    v2 = Buffer;
  }
  v4 = -1;
  do
    ++v4;
  while ( v2[v4] );
  if ( v4 >= 0x7FFFFFFE )
  {
    pExceptionObject[0] = 4;
    throw (TestException *)pExceptionObject;
  }
  TestMemory = (unsigned __int16 *)AllocateTestMemory(2 * v4 + 2);
  if ( (unsigned int)StringCchCopyW(TestMemory, v4 + 1, v2) )
  {
    FreeTestMemory(v6);
    pExceptionObject[0] = 4;
    throw (TestException *)pExceptionObject;
  }
  *a1 = (unsigned __int16 *)v6;
}

```

## disassembly

```asm
0x18000e594  mov     [rsp+arg_10], rbx
0x18000e599  push    rbp
0x18000e59a  push    rsi
0x18000e59b  push    rdi
0x18000e59c  sub     rsp, 440h
0x18000e5a3  mov     rax, cs:__security_cookie
0x18000e5aa  xor     rax, rsp
0x18000e5ad  mov     [rsp+458h+var_28], rax
0x18000e5b5  xor     ebp, ebp
0x18000e5b7  mov     rdi, rdx
0x18000e5ba  mov     rsi, rcx
0x18000e5bd  cmp     rdx, 10000h
0x18000e5c4  jnb     short loc_18000E5EA
0x18000e5c6  mov     rcx, cs:off_18001B080; hInstance
0x18000e5cd  lea     r8, [rsp+458h+Buffer]; lpBuffer
0x18000e5d2  movzx   edx, dx; uID
0x18000e5d5  mov     r9d, 200h; cchBufferMax
0x18000e5db  call    cs:__imp_LoadStringW
0x18000e5e1  test    eax, eax
0x18000e5e3  js      short loc_18000E649
0x18000e5e5  lea     rdi, [rsp+458h+Buffer]
0x18000e5ea  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e5ee  inc     rbx
0x18000e5f1  cmp     [rdi+rbx*2], bp
0x18000e5f5  jnz     short loc_18000E5EE
0x18000e5f7  cmp     rbx, 7FFFFFFEh
0x18000e5fe  jnb     short loc_18000E663
0x18000e600  lea     rcx, ds:2[rbx*2]; unsigned __int64
0x18000e608  call    ?AllocateTestMemory@@YAPEAX_K@Z; AllocateTestMemory(unsigned __int64)
0x18000e60d  lea     rdx, [rbx+1]; unsigned __int64
0x18000e611  mov     r8, rdi; unsigned __int16 *
0x18000e614  mov     rcx, rax; unsigned __int16 *
0x18000e617  mov     r11, rax
0x18000e61a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e61f  test    eax, eax
0x18000e621  jnz     short loc_18000E67D
0x18000e623  mov     [rsi], r11
0x18000e626  mov     rcx, [rsp+458h+var_28]
0x18000e62e  xor     rcx, rsp; StackCookie
0x18000e631  call    __security_check_cookie
0x18000e636  mov     rbx, [rsp+458h+arg_10]
0x18000e63e  add     rsp, 440h
0x18000e645  pop     rdi
0x18000e646  pop     rsi
0x18000e647  pop     rbp
0x18000e648  retn
0x18000e649  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e650  mov     [rsp+458h+pExceptionObject], 4
0x18000e658  lea     rcx, [rsp+458h+pExceptionObject]; pExceptionObject
0x18000e65d  call    _CxxThrowException_0
0x18000e663  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e66a  mov     [rsp+458h+pExceptionObject], 4
0x18000e672  lea     rcx, [rsp+458h+pExceptionObject]; pExceptionObject
0x18000e677  call    _CxxThrowException_0
0x18000e67d  mov     rcx, r11; pv
0x18000e680  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x18000e685  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e68c  mov     [rsp+458h+pExceptionObject], 4
0x18000e694  lea     rcx, [rsp+458h+pExceptionObject]; pExceptionObject
0x18000e699  call    _CxxThrowException_0
```
