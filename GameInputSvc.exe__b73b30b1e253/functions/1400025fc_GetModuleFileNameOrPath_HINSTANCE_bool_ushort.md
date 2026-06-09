# GetModuleFileNameOrPath(HINSTANCE__ *,bool,ushort * *)

- ea: `0x1400025fc`
- end: `0x140002791`
- name: `?GetModuleFileNameOrPath@@YAJPEAUHINSTANCE__@@_NPEAPEAG@Z`
- size: `405`
- prototype: `__int64 __fastcall(HINSTANCE, char, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x140003e54`

## callees

- `0x140001008`
- `0x1400025fc`
- `0x140006b48`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140002643`
- `ntdll!RtlAllocateHeap` at `0x140002643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002681`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002681`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000265d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000265d`

## pseudocode

```c
__int64 __fastcall GetModuleFileNameOrPath(HINSTANCE a1, char a2, unsigned __int16 **a3)
{
  DWORD i; // ebx
  SIZE_T v5; // rax
  WCHAR *Heap; // rax
  int v7; // r8d
  int v8; // r9d
  WCHAR *v9; // rdi
  DWORD ModuleFileNameW; // eax
  DWORD LastError; // ebx
  int v13; // r8d
  int v14; // r9d
  HINSTANCE v15; // [rsp+60h] [rbp+20h] BYREF
  int v16; // [rsp+68h] [rbp+28h] BYREF
  const char *v17; // [rsp+78h] [rbp+38h] BYREF

  LOBYTE(v16) = a2;
  v15 = a1;
  for ( i = 40; ; i *= 2 )
  {
    v5 = 2LL * i;
    if ( !is_mul_ok(i, 2u) )
      v5 = -1;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    v9 = Heap;
    if ( !Heap )
      break;
    ModuleFileNameW = GetModuleFileNameW(0, Heap, i);
    if ( !ModuleFileNameW )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_14000E000 > 2
        && (qword_14000E010 & 0x800) != 0
        && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v16 = LastError;
        v17 = "onecore\\xbox\\gameinput\\published\\svc\\util.cpp";
        LODWORD(v15) = 166;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          2048,
          (unsigned int)word_14000A532,
          v13,
          v14,
          (__int64)&v17,
          (__int64)&v15,
          (__int64)&v16);
      }
      if ( LastError )
      {
        if ( (int)LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2147418113;
      }
      operator delete[](v9);
      return LastError;
    }
    if ( ModuleFileNameW != i )
    {
      *a3 = v9;
      return 0;
    }
    operator delete[](v9);
  }
  LastError = -2147024882;
  if ( (unsigned int)dword_14000E000 > 2
    && (qword_14000E010 & 0x800) != 0
    && (qword_14000E018 & 0x800) == qword_14000E018 )
  {
    v16 = -2147024882;
    LODWORD(v15) = 163;
    v17 = "onecore\\xbox\\gameinput\\published\\svc\\util.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&v17,
      (unsigned int)word_14000A572,
      v7,
      v8,
      (__int64)&v17,
      (__int64)&v15,
      (__int64)&v16);
  }
  return LastError;
}

```

## disassembly

```asm
0x1400025fc  mov     [rsp-18h+arg_10], rbx
0x140002601  mov     byte ptr [rsp-18h+arg_8], dl
0x140002605  mov     [rsp-18h+arg_0], rcx
0x14000260a  push    rbp
0x14000260b  push    rsi
0x14000260c  push    rdi
0x14000260d  mov     rbp, rsp
0x140002610  sub     rsp, 40h
0x140002614  mov     rsi, r8
0x140002617  mov     ebx, 28h ; '('
0x14000261c  mov     ecx, ebx
0x14000261e  mov     eax, 2
0x140002623  mul     rcx
0x140002626  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000262d  cmovb   rax, rcx
0x140002631  mov     rcx, gs:60h
0x14000263a  mov     r8, rax; Size
0x14000263d  xor     edx, edx; Flags
0x14000263f  mov     rcx, [rcx+30h]; HeapHandle
0x140002643  call    cs:__imp_RtlAllocateHeap
0x140002649  mov     rdi, rax
0x14000264c  test    rax, rax
0x14000264f  jz      loc_140002713
0x140002655  mov     r8d, ebx; nSize
0x140002658  mov     rdx, rax; lpFilename
0x14000265b  xor     ecx, ecx; hModule
0x14000265d  call    cs:__imp_GetModuleFileNameW
0x140002663  test    eax, eax
0x140002665  jz      short loc_140002681
0x140002667  cmp     eax, ebx
0x140002669  jnz     short loc_140002677
0x14000266b  mov     rcx, rdi; P
0x14000266e  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140002673  add     ebx, ebx
0x140002675  jmp     short loc_14000261C
0x140002677  mov     [rsi], rdi
0x14000267a  xor     eax, eax
0x14000267c  jmp     loc_140002784
0x140002681  call    cs:__imp_GetLastError
0x140002687  mov     ebx, eax
0x140002689  mov     eax, cs:dword_14000E000
0x14000268f  cmp     eax, 2
0x140002692  jbe     short loc_1400026F3
0x140002694  mov     rdx, cs:qword_14000E018
0x14000269b  mov     ecx, 800h
0x1400026a0  mov     rax, cs:qword_14000E010
0x1400026a7  test    rcx, rax
0x1400026aa  jz      short loc_1400026F3
0x1400026ac  mov     rax, rdx
0x1400026af  and     rax, rcx
0x1400026b2  cmp     rax, rdx
0x1400026b5  jnz     short loc_1400026F3
0x1400026b7  lea     rax, aOnecoreXboxGam_1; "onecore\\xbox\\gameinput\\published\\sv"...
0x1400026be  mov     [rbp+arg_8], ebx
0x1400026c1  mov     [rbp+arg_18], rax
0x1400026c5  lea     rdx, word_14000A532
0x1400026cc  lea     rax, [rbp+arg_8]
0x1400026d0  mov     dword ptr [rbp+arg_0], 0A6h
0x1400026d7  mov     [rsp+40h+var_10], rax
0x1400026dc  lea     rax, [rbp+arg_0]
0x1400026e0  mov     [rsp+40h+var_18], rax
0x1400026e5  lea     rax, [rbp+arg_18]
0x1400026e9  mov     [rsp+40h+var_20], rax
0x1400026ee  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400026f3  test    ebx, ebx
0x1400026f5  jnz     short loc_1400026FE
0x1400026f7  mov     ebx, 8000FFFFh
0x1400026fc  jmp     short loc_140002709
0x1400026fe  jle     short loc_140002709
0x140002700  movzx   ebx, bx
0x140002703  or      ebx, 80070000h
0x140002709  mov     rcx, rdi; P
0x14000270c  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140002711  jmp     short loc_140002782
0x140002713  mov     eax, cs:dword_14000E000
0x140002719  mov     ebx, 8007000Eh
0x14000271e  cmp     eax, 2
0x140002721  jbe     short loc_140002782
0x140002723  mov     rdx, cs:qword_14000E018
0x14000272a  mov     ecx, 800h
0x14000272f  mov     rax, cs:qword_14000E010
0x140002736  test    rcx, rax
0x140002739  jz      short loc_140002782
0x14000273b  mov     rax, rdx
0x14000273e  and     rax, rcx
0x140002741  cmp     rax, rdx
0x140002744  jnz     short loc_140002782
0x140002746  lea     rcx, [rbp+arg_8]
0x14000274a  mov     [rbp+arg_8], ebx
0x14000274d  mov     [rsp+40h+var_10], rcx
0x140002752  lea     rax, aOnecoreXboxGam_1; "onecore\\xbox\\gameinput\\published\\sv"...
0x140002759  lea     rcx, [rbp+arg_0]
0x14000275d  mov     dword ptr [rbp+arg_0], 0A3h
0x140002764  mov     [rsp+40h+var_18], rcx
0x140002769  lea     rdx, word_14000A572
0x140002770  lea     rcx, [rbp+arg_18]
0x140002774  mov     [rbp+arg_18], rax
0x140002778  mov     [rsp+40h+var_20], rcx
0x14000277d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140002782  mov     eax, ebx
0x140002784  mov     rbx, [rsp+40h+arg_10]
0x140002789  add     rsp, 40h
0x14000278d  pop     rdi
0x14000278e  pop     rsi
0x14000278f  pop     rbp
0x140002790  retn
```
