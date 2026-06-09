# Mp2DemuxSec::CDemuxSec::CreateSids(void)

- ea: `0x1800184fc`
- end: `0x180018659`
- name: `?CreateSids@CDemuxSec@Mp2DemuxSec@@AEAAJXZ`
- size: `349`
- prototype: `__int64 __fastcall(Mp2DemuxSec::CDemuxSec *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180011d44`
- `0x180012520`
- `0x180013a58`

## callees

- `0x180001054`
- `0x180001e98`
- `0x1800184fc`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018635`
- `KERNEL32!GetLastError` at `0x180018635`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800185ce`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18001862b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800185ce`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18001862b`

## pseudocode

```c
__int64 __fastcall Mp2DemuxSec::CDemuxSec::CreateSids(Mp2DemuxSec::CDemuxSec *this)
{
  __int64 v2; // rax
  unsigned __int64 v3; // r14
  void *v4; // rax
  unsigned int v5; // ebx
  unsigned int v6; // ebp
  PSID *pSid; // rbx
  DWORD v8; // edi
  struct _SID_IDENTIFIER_AUTHORITY *v9; // rax
  struct _SID_IDENTIFIER_AUTHORITY *v10; // rax
  signed int LastError; // eax

  if ( *((_QWORD *)this + 6) )
    goto LABEL_7;
  v2 = *(_QWORD *)this;
  *((_BYTE *)this + 56) = 0;
  v3 = (*(unsigned __int8 (**)(void))(v2 + 8))();
  v4 = operator new[](saturated_mul(v3, 8u));
  *((_QWORD *)this + 6) = v4;
  if ( !v4 )
    return (unsigned int)-2147024882;
  memset_0(v4, 0, 8 * v3);
  *((_BYTE *)this + 56) = 0;
  v6 = 0;
  if ( !(_DWORD)v3 )
  {
LABEL_7:
    v5 = 0;
    if ( *((_QWORD *)this + 8) )
      return v5;
    v10 = (struct _SID_IDENTIFIER_AUTHORITY *)(*(__int64 (__fastcall **)(Mp2DemuxSec::CDemuxSec *))(*(_QWORD *)this
                                                                                                  + 24LL))(this);
    if ( AllocateAndInitializeSid(v10, 1u, 0, 0, 0, 0, 0, 0, 0, 0, (PSID *)this + 8) )
      return v5;
  }
  else
  {
    while ( 1 )
    {
      pSid = (PSID *)(*((_QWORD *)this + 6) + 8LL * v6);
      v8 = (**(__int64 (__fastcall ***)(Mp2DemuxSec::CDemuxSec *, _QWORD))this)(this, v6);
      v9 = (struct _SID_IDENTIFIER_AUTHORITY *)(*(__int64 (__fastcall **)(Mp2DemuxSec::CDemuxSec *))(*(_QWORD *)this + 16LL))(this);
      if ( !AllocateAndInitializeSid(v9, 1u, v8, 0, 0, 0, 0, 0, 0, 0, pSid) )
        break;
      ++*((_BYTE *)this + 56);
      if ( ++v6 >= (unsigned int)v3 )
        goto LABEL_7;
    }
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v5;
}

```

## disassembly

```asm
0x1800184fc  push    rbx
0x1800184fe  push    rbp
0x1800184ff  push    rsi
0x180018500  push    rdi
0x180018501  push    r14
0x180018503  push    r15
0x180018505  sub     rsp, 68h
0x180018509  xor     r15d, r15d
0x18001850c  mov     rsi, rcx
0x18001850f  cmp     [rcx+30h], r15
0x180018513  jnz     loc_1800185E2
0x180018519  mov     rax, [rcx]
0x18001851c  mov     [rcx+38h], r15b
0x180018520  mov     rax, [rax+8]
0x180018524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018529  movzx   r14d, al
0x18001852d  lea     rcx, [r15-1]
0x180018531  lea     eax, [r15+8]
0x180018535  mul     r14
0x180018538  cmovb   rax, rcx
0x18001853c  mov     rcx, rax; unsigned __int64
0x18001853f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180018544  mov     [rsi+30h], rax
0x180018548  test    rax, rax
0x18001854b  jnz     short loc_180018557
0x18001854d  mov     ebx, 8007000Eh
0x180018552  jmp     loc_18001864A
0x180018557  lea     r8, ds:0[r14*8]; Size
0x18001855f  xor     edx, edx; Val
0x180018561  mov     rcx, rax; void *
0x180018564  call    memset_0
0x180018569  mov     [rsi+38h], r15b
0x18001856d  mov     ebp, r15d
0x180018570  test    r14d, r14d
0x180018573  jz      short loc_1800185E2
0x180018575  mov     rax, [rsi+30h]
0x180018579  mov     edx, ebp
0x18001857b  mov     ecx, ebp
0x18001857d  lea     rbx, [rax+rcx*8]
0x180018581  mov     rax, [rsi]
0x180018584  mov     rcx, rsi
0x180018587  mov     rax, [rax]
0x18001858a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001858f  mov     rcx, [rsi]
0x180018592  mov     edi, eax
0x180018594  mov     rax, [rcx+10h]
0x180018598  mov     rcx, rsi
0x18001859b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185a0  mov     [rsp+98h+pSid], rbx; pSid
0x1800185a5  xor     r9d, r9d; nSubAuthority1
0x1800185a8  mov     [rsp+98h+nSubAuthority7], r15d; nSubAuthority7
0x1800185ad  mov     r8d, edi; nSubAuthority0
0x1800185b0  mov     [rsp+98h+nSubAuthority6], r15d; nSubAuthority6
0x1800185b5  mov     dl, 1; nSubAuthorityCount
0x1800185b7  mov     [rsp+98h+nSubAuthority5], r15d; nSubAuthority5
0x1800185bc  mov     rcx, rax; pIdentifierAuthority
0x1800185bf  mov     [rsp+98h+nSubAuthority4], r15d; nSubAuthority4
0x1800185c4  mov     [rsp+98h+nSubAuthority3], r15d; nSubAuthority3
0x1800185c9  mov     [rsp+98h+nSubAuthority2], r15d; nSubAuthority2
0x1800185ce  call    cs:__imp_AllocateAndInitializeSid
0x1800185d4  test    eax, eax
0x1800185d6  jz      short loc_180018635
0x1800185d8  inc     byte ptr [rsi+38h]
0x1800185db  inc     ebp
0x1800185dd  cmp     ebp, r14d
0x1800185e0  jb      short loc_180018575
0x1800185e2  lea     rdi, [rsi+40h]
0x1800185e6  mov     ebx, r15d
0x1800185e9  cmp     [rdi], r15
0x1800185ec  jnz     short loc_18001864A
0x1800185ee  mov     rax, [rsi]
0x1800185f1  mov     rcx, rsi
0x1800185f4  mov     rax, [rax+18h]
0x1800185f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185fd  mov     [rsp+98h+pSid], rdi; pSid
0x180018602  mov     rcx, rax; pIdentifierAuthority
0x180018605  mov     [rsp+98h+nSubAuthority7], r15d; nSubAuthority7
0x18001860a  xor     r9d, r9d; nSubAuthority1
0x18001860d  mov     [rsp+98h+nSubAuthority6], r15d; nSubAuthority6
0x180018612  xor     r8d, r8d; nSubAuthority0
0x180018615  mov     [rsp+98h+nSubAuthority5], r15d; nSubAuthority5
0x18001861a  mov     dl, 1; nSubAuthorityCount
0x18001861c  mov     [rsp+98h+nSubAuthority4], r15d; nSubAuthority4
0x180018621  mov     [rsp+98h+nSubAuthority3], r15d; nSubAuthority3
0x180018626  mov     [rsp+98h+nSubAuthority2], r15d; nSubAuthority2
0x18001862b  call    cs:__imp_AllocateAndInitializeSid
0x180018631  test    eax, eax
0x180018633  jnz     short loc_18001864A
0x180018635  call    cs:__imp_GetLastError
0x18001863b  mov     ebx, eax
0x18001863d  test    eax, eax
0x18001863f  jle     short loc_18001864A
0x180018641  movzx   ebx, ax
0x180018644  or      ebx, 80070000h
0x18001864a  mov     eax, ebx
0x18001864c  add     rsp, 68h
0x180018650  pop     r15
0x180018652  pop     r14
0x180018654  pop     rdi
0x180018655  pop     rsi
0x180018656  pop     rbp
0x180018657  pop     rbx
0x180018658  retn
```
