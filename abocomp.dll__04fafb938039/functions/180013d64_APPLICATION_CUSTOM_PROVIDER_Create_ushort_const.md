# APPLICATION_CUSTOM_PROVIDER::Create(ushort const *)

- ea: `0x180013d64`
- end: `0x180013e06`
- name: `?Create@APPLICATION_CUSTOM_PROVIDER@@QEAAJPEBG@Z`
- size: `162`
- prototype: `__int64 __fastcall(APPLICATION_CUSTOM_PROVIDER *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180014488`
- `0x180016b1c`

## callees

- `0x180001f90`
- `0x180013d64`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180013dc1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180013dc1`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180013dd5`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180013dd5`

## pseudocode

```c
__int64 __fastcall APPLICATION_CUSTOM_PROVIDER::Create(APPLICATION_CUSTOM_PROVIDER *this, const unsigned __int16 *a2)
{
  int v4; // ebx
  const unsigned __int16 *v5; // rdx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v8; // [rsp+40h] [rbp+8h] BYREF

  v8 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(**((_QWORD **)this + 3) + 64LL))(
         *((_QWORD *)this + 3),
         L"applicationPool",
         &v8,
         0,
         0);
  if ( v4 < 0 )
  {
    if ( !a2 )
    {
LABEL_6:
      Str = STRU::QueryStr((STRU *)(*((_QWORD *)this + 2) + 56LL));
      ABO_MAPPER_LOG::WriteLogEntry(
        (HANDLE *)g_pAboLog,
        L"Failed to Get AppPoolName for Application associated with node (%s).  error = %08x\n",
        Str,
        (unsigned int)v4);
      return (unsigned int)v4;
    }
    v5 = a2;
  }
  else
  {
    v5 = v8;
  }
  v4 = STRU::Copy((APPLICATION_CUSTOM_PROVIDER *)((char *)this + 40), v5);
  if ( v4 < 0 )
    goto LABEL_6;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013d64  mov     r11, rsp
0x180013d67  mov     [r11+10h], rbx
0x180013d6b  mov     [r11+18h], rsi
0x180013d6f  push    rdi
0x180013d70  sub     rsp, 30h
0x180013d74  mov     rdi, rcx
0x180013d77  mov     qword ptr [r11+8], 0
0x180013d7f  mov     rcx, [rcx+18h]
0x180013d83  lea     r8, [r11+8]
0x180013d87  mov     rsi, rdx
0x180013d8a  mov     qword ptr [r11-18h], 0
0x180013d92  xor     r9d, r9d
0x180013d95  lea     rdx, aApplicationpoo_0; "applicationPool"
0x180013d9c  mov     rax, [rcx]
0x180013d9f  mov     rax, [rax+40h]
0x180013da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013da8  mov     ebx, eax
0x180013daa  test    eax, eax
0x180013dac  js      short loc_180013DB5
0x180013dae  mov     rdx, [rsp+38h+arg_0]
0x180013db3  jmp     short loc_180013DBD
0x180013db5  test    rsi, rsi
0x180013db8  jz      short loc_180013DCD
0x180013dba  mov     rdx, rsi
0x180013dbd  lea     rcx, [rdi+28h]
0x180013dc1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180013dc7  mov     ebx, eax
0x180013dc9  test    eax, eax
0x180013dcb  jns     short loc_180013DF4
0x180013dcd  mov     rcx, [rdi+10h]
0x180013dd1  add     rcx, 38h ; '8'
0x180013dd5  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180013ddb  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180013de2  lea     rdx, aFailedToGetApp_1; "Failed to Get AppPoolName for Applicati"...
0x180013de9  mov     r8, rax
0x180013dec  mov     r9d, ebx
0x180013def  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180013df4  mov     rsi, [rsp+38h+arg_10]
0x180013df9  mov     eax, ebx
0x180013dfb  mov     rbx, [rsp+38h+arg_8]
0x180013e00  add     rsp, 30h
0x180013e04  pop     rdi
0x180013e05  retn
```
