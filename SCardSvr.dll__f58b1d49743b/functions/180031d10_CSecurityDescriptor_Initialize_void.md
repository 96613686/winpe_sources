# CSecurityDescriptor::Initialize(void)

- ea: `0x180031d10`
- end: `0x180031de9`
- name: `?Initialize@CSecurityDescriptor@@QEAAJXZ`
- size: `217`
- prototype: `__int64 __fastcall(CSecurityDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800297a0`

## callees

- `0x18001c330`
- `0x18001c370`
- `0x180023168`
- `0x180031d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031db4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031db4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180031daa`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180031daa`

## pseudocode

```c
__int64 __fastcall CSecurityDescriptor::Initialize(CSecurityDescriptor *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rax
  __int64 result; // rax
  signed int LastError; // eax
  unsigned int v10; // edi

  v2 = *(void **)this;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)this = 0;
  }
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    operator delete[](v3);
    *((_QWORD *)this + 1) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    operator delete[](v4);
    *((_QWORD *)this + 2) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
  {
    operator delete[](v5);
    *((_QWORD *)this + 3) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 4);
  if ( v6 )
  {
    operator delete[](v6);
    *((_QWORD *)this + 4) = 0;
  }
  v7 = operator new(0x28u);
  *(_QWORD *)this = v7;
  if ( !v7 )
    return 2147942414LL;
  if ( InitializeSecurityDescriptor(v7, 1u) )
    return 0;
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  operator delete(*(void **)this);
  result = v10;
  *(_QWORD *)this = 0;
  return result;
}

```

## disassembly

```asm
0x180031d10  mov     [rsp+arg_0], rbx
0x180031d15  push    rdi
0x180031d16  sub     rsp, 20h
0x180031d1a  mov     rbx, rcx
0x180031d1d  mov     rcx, [rcx]; Block
0x180031d20  test    rcx, rcx
0x180031d23  jz      short loc_180031D31
0x180031d25  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031d2a  mov     qword ptr [rbx], 0
0x180031d31  mov     rcx, [rbx+8]; Block
0x180031d35  test    rcx, rcx
0x180031d38  jz      short loc_180031D47
0x180031d3a  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180031d3f  mov     qword ptr [rbx+8], 0
0x180031d47  mov     rcx, [rbx+10h]; Block
0x180031d4b  test    rcx, rcx
0x180031d4e  jz      short loc_180031D5D
0x180031d50  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180031d55  mov     qword ptr [rbx+10h], 0
0x180031d5d  mov     rcx, [rbx+18h]; Block
0x180031d61  test    rcx, rcx
0x180031d64  jz      short loc_180031D73
0x180031d66  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180031d6b  mov     qword ptr [rbx+18h], 0
0x180031d73  mov     rcx, [rbx+20h]; Block
0x180031d77  test    rcx, rcx
0x180031d7a  jz      short loc_180031D89
0x180031d7c  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180031d81  mov     qword ptr [rbx+20h], 0
0x180031d89  mov     ecx, 28h ; '('; Size
0x180031d8e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031d93  mov     [rbx], rax
0x180031d96  test    rax, rax
0x180031d99  jnz     short loc_180031DA2
0x180031d9b  mov     eax, 8007000Eh
0x180031da0  jmp     short loc_180031DDE
0x180031da2  mov     edx, 1; dwRevision
0x180031da7  mov     rcx, rax; pSecurityDescriptor
0x180031daa  call    cs:__imp_InitializeSecurityDescriptor
0x180031db0  test    eax, eax
0x180031db2  jnz     short loc_180031DDC
0x180031db4  call    cs:__imp_GetLastError
0x180031dba  mov     edi, eax
0x180031dbc  test    eax, eax
0x180031dbe  jle     short loc_180031DC9
0x180031dc0  movzx   edi, ax
0x180031dc3  or      edi, 80070000h
0x180031dc9  mov     rcx, [rbx]; Block
0x180031dcc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031dd1  mov     eax, edi
0x180031dd3  mov     qword ptr [rbx], 0
0x180031dda  jmp     short loc_180031DDE
0x180031ddc  xor     eax, eax
0x180031dde  mov     rbx, [rsp+28h+arg_0]
0x180031de3  add     rsp, 20h
0x180031de7  pop     rdi
0x180031de8  retn
```
