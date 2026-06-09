# BrowserToolThreadWindow::OnCreateBrowserTool(uint,unsigned __int64,__int64,int &)

- ea: `0x180008520`
- end: `0x180008680`
- name: `?OnCreateBrowserTool@BrowserToolThreadWindow@@QEAA_JI_K_JAEAH@Z`
- size: `352`
- prototype: `__int64(BrowserToolThreadWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008dc0`

## callees

- `0x180001900`
- `0x180005b20`
- `0x180006e00`
- `0x180007728`
- `0x180008520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000861c`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000861c`
- `KERNEL32!EnterCriticalSection` at `0x180008584`
- `KERNEL32!EnterCriticalSection` at `0x180008584`
- `KERNEL32!LeaveCriticalSection` at `0x1800085b3`
- `KERNEL32!LeaveCriticalSection` at `0x1800085b3`
- `KERNEL32!GetCurrentThreadId` at `0x180008571`
- `KERNEL32!GetCurrentThreadId` at `0x180008571`
- `USER32!PostMessageW` at `0x18000865d`
- `USER32!PostMessageW` at `0x18000865d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BrowserToolThreadWindow::OnCreateBrowserTool(HWND *this, __int64 a2, __int64 a3, __int64 *a4)
{
  int v6; // esi
  DWORD CurrentThreadId; // ebx
  struct ATL::CAtlModule *v8; // rsi
  int v9; // edx
  int v10; // ecx
  __int64 v11; // rbx
  int v12; // esi
  unsigned int v13; // esi
  bool v14; // sf
  __int64 v15; // rax
  unsigned __int64 *v16; // rdx
  __int64 *v18; // [rsp+60h] [rbp+18h] BYREF

  v18 = a4;
  v6 = BrowserToolThreadWindow::CreateBrowser((__int64)this, &v18);
  if ( a4 )
  {
    BrowserInitializeParams::~BrowserInitializeParams((BrowserInitializeParams *)a4);
    operator delete(a4);
  }
  if ( !v6 && this[12] )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = ATL::_pAtlModule;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
    v9 = *((_DWORD *)qword_180050788 + 4);
    if ( v9 <= 0 )
      goto LABEL_9;
    v10 = 0;
    while ( *(_DWORD *)(*(_QWORD *)qword_180050788 + 4LL * v10) != CurrentThreadId )
    {
      if ( ++v10 >= v9 )
        goto LABEL_9;
    }
    if ( v10 == -1 )
    {
LABEL_9:
      v11 = 0;
    }
    else
    {
      if ( v10 < 0 || v10 >= v9 )
      {
        Microsoft::WRL::Details::RaiseException(
          (Microsoft::WRL::Details *)0xC000008CLL,
          v9,
          (unsigned int)qword_180050788);
        JUMPOUT(0x18000867FLL);
      }
      _mm_lfence();
      v11 = *(_QWORD *)(*((_QWORD *)qword_180050788 + 1) + 8LL * v10);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 24));
    v12 = *(_DWORD *)(v11 + 16);
    if ( v12 != *(_DWORD *)(v11 + 20) )
      goto LABEL_21;
    if ( *(_DWORD *)(v11 + 20) )
    {
      v14 = (v12 & 0x40000000) != 0;
      v13 = 2 * v12;
      if ( v14 )
        goto LABEL_24;
    }
    else
    {
      v13 = 1;
    }
    if ( v13 <= 0xFFFFFFFuLL )
    {
      v15 = _o__recalloc(*(_QWORD *)(v11 + 8), v13, 8);
      if ( v15 )
      {
        *(_DWORD *)(v11 + 20) = v13;
        *(_QWORD *)(v11 + 8) = v15;
LABEL_21:
        v16 = (unsigned __int64 *)(*(_QWORD *)(v11 + 8) + 8LL * *(int *)(v11 + 16));
        if ( v16 )
          *v16 = (unsigned __int64)(this + 9) & -(__int64)(this != 0);
        ++*(_DWORD *)(v11 + 16);
      }
    }
LABEL_24:
    PostMessageW(this[16], 0x798u, *((int *)this + 30), *((_QWORD *)this[12] + 1));
    return 0;
  }
  return -1;
}

```

## disassembly

```asm
0x180008520  mov     [rsp+arg_10], r8
0x180008525  push    rbx
0x180008526  push    rbp
0x180008527  push    rsi
0x180008528  push    rdi
0x180008529  sub     rsp, 28h
0x18000852d  mov     rbx, r9
0x180008530  mov     rdi, rcx
0x180008533  mov     [rsp+48h+arg_10], rbx
0x180008538  lea     rdx, [rsp+48h+arg_10]
0x18000853d  call    ?CreateBrowser@BrowserToolThreadWindow@@AEAAJAEAV?$unique_ptr@UBrowserInitializeParams@@U?$default_delete@UBrowserInitializeParams@@@std@@@std@@@Z; BrowserToolThreadWindow::CreateBrowser(std::unique_ptr<BrowserInitializeParams> &)
0x180008542  mov     esi, eax
0x180008544  test    rbx, rbx
0x180008547  jz      short loc_18000855E
0x180008549  mov     rcx, rbx; this
0x18000854c  call    ??1BrowserInitializeParams@@QEAA@XZ; BrowserInitializeParams::~BrowserInitializeParams(void)
0x180008551  mov     edx, 78h ; 'x'
0x180008556  mov     rcx, rbx; Block
0x180008559  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000855e  test    esi, esi
0x180008560  jnz     loc_180008668
0x180008566  cmp     qword ptr [rdi+60h], 0
0x18000856b  jz      loc_180008668
0x180008571  call    cs:__imp_GetCurrentThreadId
0x180008577  mov     ebx, eax
0x180008579  mov     rsi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008580  lea     rcx, [rsi+18h]; lpCriticalSection
0x180008584  call    cs:__imp_EnterCriticalSection
0x18000858a  mov     r8, cs:qword_180050788; unsigned int
0x180008591  mov     edx, [r8+10h]; int
0x180008595  test    edx, edx
0x180008597  jle     short loc_1800085AD
0x180008599  xor     ecx, ecx
0x18000859b  mov     r9, [r8]
0x18000859e  movsxd  rax, ecx
0x1800085a1  cmp     [r9+rax*4], ebx
0x1800085a5  jz      short loc_1800085DE
0x1800085a7  inc     ecx
0x1800085a9  cmp     ecx, edx
0x1800085ab  jl      short loc_18000859E
0x1800085ad  xor     ebx, ebx
0x1800085af  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800085b3  call    cs:__imp_LeaveCriticalSection
0x1800085b9  mov     rax, rdi
0x1800085bc  lea     rcx, [rdi+48h]
0x1800085c0  neg     rax
0x1800085c3  sbb     rbp, rbp
0x1800085c6  and     rbp, rcx
0x1800085c9  mov     esi, [rbx+10h]
0x1800085cc  cmp     esi, [rbx+14h]
0x1800085cf  jnz     short loc_18000862E
0x1800085d1  cmp     dword ptr [rbx+14h], 0
0x1800085d5  jnz     short loc_180008603
0x1800085d7  mov     esi, 1
0x1800085dc  jmp     short loc_180008607
0x1800085de  cmp     ecx, 0FFFFFFFFh
0x1800085e1  jz      short loc_1800085AD
0x1800085e3  test    ecx, ecx
0x1800085e5  js      loc_180008675
0x1800085eb  cmp     ecx, edx
0x1800085ed  jge     loc_180008675
0x1800085f3  lfence
0x1800085f6  movsxd  rcx, ecx
0x1800085f9  mov     rax, [r8+8]
0x1800085fd  mov     rbx, [rax+rcx*8]
0x180008601  jmp     short loc_1800085AF
0x180008603  add     esi, esi
0x180008605  js      short loc_180008645
0x180008607  mov     edx, esi
0x180008609  cmp     rdx, 0FFFFFFFh
0x180008610  ja      short loc_180008645
0x180008612  mov     r8d, 8
0x180008618  mov     rcx, [rbx+8]
0x18000861c  call    cs:__imp__o__recalloc
0x180008622  test    rax, rax
0x180008625  jz      short loc_180008645
0x180008627  mov     [rbx+14h], esi
0x18000862a  mov     [rbx+8], rax
0x18000862e  movsxd  rcx, dword ptr [rbx+10h]
0x180008632  mov     rax, [rbx+8]
0x180008636  lea     rdx, [rax+rcx*8]
0x18000863a  test    rdx, rdx
0x18000863d  jz      short loc_180008642
0x18000863f  mov     [rdx], rbp
0x180008642  inc     dword ptr [rbx+10h]
0x180008645  mov     r9, [rdi+60h]
0x180008649  movsxd  r8, dword ptr [rdi+78h]; wParam
0x18000864d  mov     r9, [r9+8]; lParam
0x180008651  mov     edx, 798h; Msg
0x180008656  mov     rcx, [rdi+80h]; hWnd
0x18000865d  call    cs:__imp_PostMessageW
0x180008663  nop
0x180008664  xor     eax, eax
0x180008666  jmp     short loc_18000866C
0x180008668  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000866c  add     rsp, 28h
0x180008670  pop     rdi
0x180008671  pop     rsi
0x180008672  pop     rbp
0x180008673  pop     rbx
0x180008674  retn
0x180008675  mov     ecx, 0C000008Ch; this
0x18000867a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
