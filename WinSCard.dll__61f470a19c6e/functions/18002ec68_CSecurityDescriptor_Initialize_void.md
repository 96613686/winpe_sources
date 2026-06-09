# CSecurityDescriptor::Initialize(void)

- ea: `0x18002ec68`
- end: `0x18002ed41`
- name: `?Initialize@CSecurityDescriptor@@QEAAJXZ`
- size: `217`
- prototype: `__int64 __fastcall(CSecurityDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180014d40`

## callees

- `0x18001b9b8`
- `0x18001b9c4`
- `0x18001ba10`
- `0x18002ec68`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002ed02`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002ed02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed0c`

## pseudocode

```c
__int64 __fastcall CSecurityDescriptor::Initialize(CSecurityDescriptor *this, unsigned __int64 a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rax
  __int64 result; // rax
  signed int LastError; // eax
  unsigned int v11; // edi

  v3 = *(void **)this;
  if ( v3 )
  {
    operator delete(v3);
    *(_QWORD *)this = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    operator delete(v4, a2);
    *((_QWORD *)this + 1) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    operator delete(v5, a2);
    *((_QWORD *)this + 2) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  if ( v6 )
  {
    operator delete(v6, a2);
    *((_QWORD *)this + 3) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 4);
  if ( v7 )
  {
    operator delete(v7, a2);
    *((_QWORD *)this + 4) = 0;
  }
  v8 = operator new(0x28u);
  *(_QWORD *)this = v8;
  if ( !v8 )
    return 2147942414LL;
  if ( InitializeSecurityDescriptor(v8, 1u) )
    return 0;
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  operator delete(*(void **)this);
  result = v11;
  *(_QWORD *)this = 0;
  return result;
}

```

## disassembly

```asm
0x18002ec68  mov     [rsp+arg_0], rbx
0x18002ec6d  push    rdi
0x18002ec6e  sub     rsp, 20h
0x18002ec72  mov     rbx, rcx
0x18002ec75  mov     rcx, [rcx]; Block
0x18002ec78  test    rcx, rcx
0x18002ec7b  jz      short loc_18002EC89
0x18002ec7d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ec82  mov     qword ptr [rbx], 0
0x18002ec89  mov     rcx, [rbx+8]; void *
0x18002ec8d  test    rcx, rcx
0x18002ec90  jz      short loc_18002EC9F
0x18002ec92  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ec97  mov     qword ptr [rbx+8], 0
0x18002ec9f  mov     rcx, [rbx+10h]; void *
0x18002eca3  test    rcx, rcx
0x18002eca6  jz      short loc_18002ECB5
0x18002eca8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ecad  mov     qword ptr [rbx+10h], 0
0x18002ecb5  mov     rcx, [rbx+18h]; void *
0x18002ecb9  test    rcx, rcx
0x18002ecbc  jz      short loc_18002ECCB
0x18002ecbe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ecc3  mov     qword ptr [rbx+18h], 0
0x18002eccb  mov     rcx, [rbx+20h]; void *
0x18002eccf  test    rcx, rcx
0x18002ecd2  jz      short loc_18002ECE1
0x18002ecd4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ecd9  mov     qword ptr [rbx+20h], 0
0x18002ece1  mov     ecx, 28h ; '('; Size
0x18002ece6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002eceb  mov     [rbx], rax
0x18002ecee  test    rax, rax
0x18002ecf1  jnz     short loc_18002ECFA
0x18002ecf3  mov     eax, 8007000Eh
0x18002ecf8  jmp     short loc_18002ED36
0x18002ecfa  mov     edx, 1; dwRevision
0x18002ecff  mov     rcx, rax; pSecurityDescriptor
0x18002ed02  call    cs:__imp_InitializeSecurityDescriptor
0x18002ed08  test    eax, eax
0x18002ed0a  jnz     short loc_18002ED34
0x18002ed0c  call    cs:__imp_GetLastError
0x18002ed12  mov     edi, eax
0x18002ed14  test    eax, eax
0x18002ed16  jle     short loc_18002ED21
0x18002ed18  movzx   edi, ax
0x18002ed1b  or      edi, 80070000h
0x18002ed21  mov     rcx, [rbx]; Block
0x18002ed24  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ed29  mov     eax, edi
0x18002ed2b  mov     qword ptr [rbx], 0
0x18002ed32  jmp     short loc_18002ED36
0x18002ed34  xor     eax, eax
0x18002ed36  mov     rbx, [rsp+28h+arg_0]
0x18002ed3b  add     rsp, 20h
0x18002ed3f  pop     rdi
0x18002ed40  retn
```
