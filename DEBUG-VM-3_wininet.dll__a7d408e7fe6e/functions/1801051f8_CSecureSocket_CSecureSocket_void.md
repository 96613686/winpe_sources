# CSecureSocket::~CSecureSocket(void)

- ea: `0x1801051f8`
- end: `0x180105495`
- name: `??1CSecureSocket@@AEAA@XZ`
- size: `669`
- prototype: `void __fastcall(CSecureSocket *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801051b0`

## callees

- `0x180025910`
- `0x180027ec0`
- `0x1800c00ec`
- `0x1800c25b4`
- `0x1800f20bc`
- `0x1801051f8`
- `0x18010549c`
- `0x18010554c`
- `0x180121810`
- `0x18014a3a4`
- `0x1801cf028`
- `0x1801e3c78`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180105311`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18010533d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180105311`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18010533d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801052b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180105456`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801052b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180105456`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180105448`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180105448`
- `SspiCli!FreeContextBuffer` at `0x180105402`
- `SspiCli!FreeContextBuffer` at `0x18010541a`
- `SspiCli!FreeContextBuffer` at `0x180105402`
- `SspiCli!FreeContextBuffer` at `0x18010541a`
- `CRYPT32!CertFreeCertificateContext` at `0x180105468`
- `CRYPT32!CertFreeCertificateContext` at `0x180105468`

## pseudocode

```c
void __fastcall CSecureSocket::~CSecureSocket(CSecureSocket *this)
{
  unsigned int *v2; // r14
  void *v3; // rbx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rbx
  SECURITY_CACHE_LIST_ENTRY *v7; // rcx
  void *v8; // r8
  const CERT_CONTEXT *v9; // rcx
  char *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned int v14; // edi
  char SourcePort; // bl
  char v16; // al
  int v17; // edx
  int v18; // r8d
  HANDLE ProcessHeap; // rax

  *(_QWORD *)this = &CSecureSocket::`vftable';
  v2 = (unsigned int *)((char *)this + 312);
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
  {
    v14 = *v2;
    SourcePort = CSecureSocket::GetSourcePort(this);
    v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 38) + 32LL))(*((_QWORD *)this + 38));
    WPP_SF_qsPdDD(
      (v14 >> 20) & 1,
      v17,
      v18,
      (_DWORD)this,
      *((_QWORD *)this + 7),
      v16,
      SourcePort,
      BYTE2(v14) & 1,
      (v14 & 0x100000) != 0);
  }
  if ( (*v2 & 0x10000) != 0 || (*v2 & 0x100000) != 0 )
  {
    v3 = (void *)*((_QWORD *)this + 10);
    if ( v3 )
    {
      FreeAuthIdentity(*((struct _SEC_WINNT_AUTH_IDENTITY_W **)this + 10));
      operator delete(v3, 0x40u);
    }
    v4 = (void *)*((_QWORD *)this + 36);
    if ( v4 )
    {
      FreeContextBuffer(v4);
      *((_QWORD *)this + 36) = 0;
      *((_DWORD *)this + 74) = 0;
    }
    CSecureSocket::TerminateSecConnection(this);
    v5 = (void *)*((_QWORD *)this + 21);
    if ( v5 )
    {
      FreeContextBuffer(v5);
      *((_QWORD *)this + 21) = 0;
      *((_DWORD *)this + 44) = 0;
    }
    if ( *((_QWORD *)this + 24) )
    {
      WxHeapFree<char>((char *)this + 192);
      *((_QWORD *)this + 24) = 0;
      *((_DWORD *)this + 50) = 0;
    }
    v6 = (void *)*((_QWORD *)this + 26);
    if ( v6 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
      *((_QWORD *)this + 26) = 0;
    }
    v7 = (SECURITY_CACHE_LIST_ENTRY *)*((_QWORD *)this + 27);
    if ( v7 )
    {
      SECURITY_CACHE_LIST_ENTRY::Release(v7);
      *((_QWORD *)this + 27) = 0;
    }
    v8 = (void *)*((_QWORD *)this + 7);
    if ( v8 )
    {
      HeapFree(g_hWxProcessHeap, 0, v8);
      *((_QWORD *)this + 7) = 0;
    }
    v9 = (const CERT_CONTEXT *)*((_QWORD *)this + 34);
    if ( v9 )
    {
      CertFreeCertificateContext(v9);
      *((_QWORD *)this + 34) = 0;
    }
  }
  v10 = (char *)this + 384;
  v11 = *((_QWORD *)this + 48);
  if ( v11 )
  {
    CServerInfo::Dereference(*(CServerInfo **)(v11 + 24));
    CServerInfo::Dereference(*(CServerInfo **)(*(_QWORD *)v10 + 32LL));
    if ( *(_QWORD *)v10 )
    {
      WxFreeHeapEx((char *)this + 384);
      *(_QWORD *)v10 = 0;
    }
  }
  v12 = *((_QWORD *)this + 38);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    *((_QWORD *)this + 38) = 0;
  }
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_(1032, 26, &WPP_e8a3628f009531a5195349498ae73e2f_Traceguids);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 8);
  v13 = *((_QWORD *)this + 38);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    *((_QWORD *)this + 38) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  CWxString::_Release((CSecureSocket *)((char *)this + 64));
}

```

## disassembly

```asm
0x1801051f8  push    rbx
0x1801051fa  push    rsi
0x1801051fb  push    rdi
0x1801051fc  push    r14
0x1801051fe  sub     rsp, 58h
0x180105202  lea     rax, ??_7CSecureSocket@@6B@; const CSecureSocket::`vftable'
0x180105209  mov     rsi, rcx
0x18010520c  mov     [rcx], rax
0x18010520f  test    byte ptr cs:xmmword_180266B60+1, 1
0x180105216  lea     r14, [rcx+138h]
0x18010521d  jnz     loc_1801053AF
0x180105223  xor     edi, edi
0x180105225  test    dword ptr [r14], 10000h
0x18010522c  jz      loc_180105355
0x180105232  mov     rbx, [rsi+50h]
0x180105236  test    rbx, rbx
0x180105239  jnz     loc_180105367
0x18010523f  mov     rcx, [rsi+120h]; pvContextBuffer
0x180105246  test    rcx, rcx
0x180105249  jnz     loc_180105402
0x18010524f  mov     rcx, rsi; this
0x180105252  call    ?TerminateSecConnection@CSecureSocket@@AEAAXXZ; CSecureSocket::TerminateSecConnection(void)
0x180105257  mov     rcx, [rsi+0A8h]; pvContextBuffer
0x18010525e  test    rcx, rcx
0x180105261  jnz     loc_18010541A
0x180105267  lea     rbx, [rsi+0C0h]
0x18010526e  cmp     [rbx], rdi
0x180105271  jnz     loc_180105432
0x180105277  mov     rbx, [rsi+0D0h]
0x18010527e  test    rbx, rbx
0x180105281  jnz     loc_180105448
0x180105287  mov     rcx, [rsi+0D8h]; this
0x18010528e  test    rcx, rcx
0x180105291  jz      short loc_18010529F
0x180105293  call    ?Release@SECURITY_CACHE_LIST_ENTRY@@QEAAJXZ; SECURITY_CACHE_LIST_ENTRY::Release(void)
0x180105298  mov     [rsi+0D8h], rdi
0x18010529f  mov     r8, [rsi+38h]; lpMem
0x1801052a3  test    r8, r8
0x1801052a6  jz      short loc_1801052BB
0x1801052a8  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1801052af  xor     edx, edx; dwFlags
0x1801052b1  call    cs:__imp_HeapFree
0x1801052b7  mov     [rsi+38h], rdi
0x1801052bb  mov     rcx, [rsi+110h]; pCertContext
0x1801052c2  test    rcx, rcx
0x1801052c5  jnz     loc_180105468
0x1801052cb  lea     rbx, [rsi+180h]
0x1801052d2  mov     rcx, [rbx]
0x1801052d5  test    rcx, rcx
0x1801052d8  jnz     loc_180105381
0x1801052de  mov     rcx, [rsi+130h]
0x1801052e5  test    rcx, rcx
0x1801052e8  jz      short loc_1801052FD
0x1801052ea  mov     rax, [rcx]
0x1801052ed  mov     rax, [rax+8]
0x1801052f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801052f6  mov     [rsi+130h], rdi
0x1801052fd  test    byte ptr cs:xmmword_180266B60+1, 1
0x180105304  jnz     loc_18010547A
0x18010530a  lea     rcx, [rsi+140h]; lpCriticalSection
0x180105311  call    cs:__imp_DeleteCriticalSection
0x180105317  mov     rcx, [rsi+130h]
0x18010531e  test    rcx, rcx
0x180105321  jz      short loc_180105336
0x180105323  mov     rax, [rcx]
0x180105326  mov     rax, [rax+8]
0x18010532a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010532f  mov     [rsi+130h], rdi
0x180105336  lea     rcx, [rsi+0E8h]; lpCriticalSection
0x18010533d  call    cs:__imp_DeleteCriticalSection
0x180105343  lea     rcx, [rsi+40h]; this
0x180105347  add     rsp, 58h
0x18010534b  pop     r14
0x18010534d  pop     rdi
0x18010534e  pop     rsi
0x18010534f  pop     rbx
0x180105350  jmp     ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x180105355  test    dword ptr [r14], 100000h
0x18010535c  jz      loc_1801052CB
0x180105362  jmp     loc_180105232
0x180105367  mov     rcx, rbx; struct _SEC_WINNT_AUTH_IDENTITY_W *
0x18010536a  call    ?FreeAuthIdentity@@YAXPEAU_SEC_WINNT_AUTH_IDENTITY_W@@@Z; FreeAuthIdentity(_SEC_WINNT_AUTH_IDENTITY_W *)
0x18010536f  mov     edx, 40h ; '@'; unsigned __int64
0x180105374  mov     rcx, rbx; void *
0x180105377  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18010537c  jmp     loc_18010523F
0x180105381  mov     rcx, [rcx+18h]; this
0x180105385  call    ?Dereference@CServerInfo@@QEAAHXZ; CServerInfo::Dereference(void)
0x18010538a  mov     rcx, [rbx]
0x18010538d  mov     rcx, [rcx+20h]; this
0x180105391  call    ?Dereference@CServerInfo@@QEAAHXZ; CServerInfo::Dereference(void)
0x180105396  cmp     [rbx], rdi
0x180105399  jz      loc_1801052DE
0x18010539f  mov     rcx, rbx
0x1801053a2  call    WxFreeHeapEx
0x1801053a7  mov     [rbx], rdi
0x1801053aa  jmp     loc_1801052DE
0x1801053af  mov     edi, [r14]
0x1801053b2  call    ?GetSourcePort@CSecureSocket@@UEBAGXZ; CSecureSocket::GetSourcePort(void)
0x1801053b7  mov     rcx, [rsi+130h]
0x1801053be  movzx   ebx, ax
0x1801053c1  mov     rax, [rcx]
0x1801053c4  mov     rax, [rax+20h]
0x1801053c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801053cd  mov     ecx, edi
0x1801053cf  mov     r9, rsi
0x1801053d2  shr     ecx, 14h
0x1801053d5  shr     edi, 10h
0x1801053d8  and     ecx, 1
0x1801053db  mov     [rsp+78h+var_38], ecx
0x1801053df  and     edi, 1
0x1801053e2  mov     [rsp+78h+var_40], edi
0x1801053e6  mov     [rsp+78h+var_48], ebx
0x1801053ea  mov     [rsp+78h+var_50], rax
0x1801053ef  mov     rax, [rsi+38h]
0x1801053f3  mov     [rsp+78h+var_58], rax
0x1801053f8  call    WPP_SF_qsPdDD
0x1801053fd  jmp     loc_180105223
0x180105402  call    cs:__imp_FreeContextBuffer
0x180105408  mov     [rsi+120h], rdi
0x18010540f  mov     [rsi+128h], edi
0x180105415  jmp     loc_18010524F
0x18010541a  call    cs:__imp_FreeContextBuffer
0x180105420  mov     [rsi+0A8h], rdi
0x180105427  mov     [rsi+0B0h], edi
0x18010542d  jmp     loc_180105267
0x180105432  mov     rcx, rbx
0x180105435  call    ??$WxHeapFree@D@@YAXPEAPEAD@Z; WxHeapFree<char>(char * *)
0x18010543a  mov     [rbx], rdi
0x18010543d  mov     [rsi+0C8h], edi
0x180105443  jmp     loc_180105277
0x180105448  call    cs:__imp_GetProcessHeap
0x18010544e  mov     r8, rbx; lpMem
0x180105451  xor     edx, edx; dwFlags
0x180105453  mov     rcx, rax; hHeap
0x180105456  call    cs:__imp_HeapFree
0x18010545c  mov     [rsi+0D0h], rdi
0x180105463  jmp     loc_180105287
0x180105468  call    cs:__imp_CertFreeCertificateContext
0x18010546e  mov     [rsi+110h], rdi
0x180105475  jmp     loc_1801052CB
0x18010547a  mov     edx, 1Ah
0x18010547f  lea     r8, WPP_e8a3628f009531a5195349498ae73e2f_Traceguids
0x180105486  mov     ecx, 408h
0x18010548b  call    WPP_SF_
0x180105490  jmp     loc_18010530A
```
