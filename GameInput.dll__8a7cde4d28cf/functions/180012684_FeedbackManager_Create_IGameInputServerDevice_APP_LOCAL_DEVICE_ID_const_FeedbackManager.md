# FeedbackManager::Create(IGameInputServerDevice *,APP_LOCAL_DEVICE_ID const *,FeedbackManager * *)

- ea: `0x180012684`
- end: `0x180012abe`
- name: `?Create@FeedbackManager@@SAJPEAUIGameInputServerDevice@@PEBUAPP_LOCAL_DEVICE_ID@@PEAPEAV1@@Z`
- size: `1082`
- prototype: `__int64 __fastcall(struct IGameInputServerDevice *, const struct APP_LOCAL_DEVICE_ID *, struct FeedbackManager **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18003197c`

## callees

- `0x180001304`
- `0x180001540`
- `0x18000c11c`
- `0x18000f800`
- `0x180012684`
- `0x180014f18`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800126b9`
- `ntdll!RtlAllocateHeap` at `0x1800126ed`
- `ntdll!RtlAllocateHeap` at `0x1800126b9`
- `ntdll!RtlAllocateHeap` at `0x1800126ed`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012890`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128a9`

## string_xrefs

- `0x180012972`: `Feedback manager created`

## pseudocode

```c
__int64 __fastcall FeedbackManager::Create(
        struct IGameInputServerDevice *a1,
        const struct APP_LOCAL_DEVICE_ID *a2,
        HANDLE **a3)
{
  HANDLE *Heap; // rax
  int v7; // r8d
  int v8; // r9d
  HANDLE *v9; // rdi
  _QWORD *v10; // rax
  __int64 v11; // rdx
  int v12; // r8d
  int v13; // r9d
  signed int LastError; // ebx
  int v15; // ecx
  __int16 *v16; // rdx
  _DWORD *v17; // r9
  const struct std::nothrow_t *v18; // rdx
  HANDLE Thread; // rax
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rcx
  const struct std::nothrow_t *v24; // rdx
  _QWORD v25[2]; // [rsp+40h] [rbp-10h] BYREF
  int v26; // [rsp+90h] [rbp+40h] BYREF
  const char *v27; // [rsp+98h] [rbp+48h] BYREF

  *a3 = 0;
  Heap = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x10u);
  v9 = Heap;
  if ( !Heap )
  {
    LastError = -2147024882;
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      v26 = -2147024882;
      v25[0] = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
      LODWORD(v27) = 165;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)word_18005D062,
        v7,
        v8,
        (__int64)v25,
        (__int64)&v27,
        (__int64)&v26);
    }
    return (unsigned int)LastError;
  }
  *Heap = 0;
  Heap[1] = 0;
  v10 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xD0u);
  if ( !v10 )
  {
    *v9 = 0;
    LastError = -2147024882;
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_35;
    v15 = qword_180069018;
    if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
      goto LABEL_35;
    LODWORD(v27) = 170;
    v16 = &word_18005CB7E;
    goto LABEL_34;
  }
  *v10 = 0;
  v10[1] = 0;
  v10[2] = 0;
  v10[3] = 0;
  v10[4] = 0;
  *((_BYTE *)v10 + 40) = 0;
  v10[6] = 0;
  v10[7] = 0;
  v10[8] = 0;
  v10[9] = 0;
  v10[10] = 0;
  *((_DWORD *)v10 + 42) = 0x1000000;
  *((_BYTE *)v10 + 204) = 1;
  v10[11] = 0;
  v10[12] = 0;
  v10[13] = 0;
  v10[14] = 0;
  v10[15] = 0;
  v10[16] = 0;
  v10[17] = 0;
  v10[18] = 0;
  v10[19] = 0;
  v10[20] = 0;
  *v9 = v10;
  LastError = FeedbackManagerState::Initialize((FeedbackManagerState *)v10, a1, a2);
  if ( LastError < 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_35;
    v11 = qword_180069018;
    v15 = qword_180069010;
    if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
      goto LABEL_35;
    LODWORD(v27) = 171;
    v16 = (__int16 *)&byte_18005BD5F;
LABEL_34:
    v25[0] = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
    v26 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v15,
      (_DWORD)v16,
      v12,
      v13,
      (__int64)v25,
      (__int64)&v27,
      (__int64)&v26);
LABEL_35:
    FeedbackManager::~FeedbackManager(v9, v11, v12, v13);
    operator delete(v9, v24);
    return (unsigned int)LastError;
  }
  v17 = *v9;
  if ( *((_DWORD *)*v9 + 12) || v17[13] || v17[20] )
  {
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)FeedbackManager::WorkerThreadProc, v17, 0, 0);
    v9[1] = Thread;
    if ( !Thread )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 )
      {
        v23 = qword_180069018 & 8;
        if ( v23 == qword_180069018 )
        {
          v26 = LastError;
          v25[0] = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
          LODWORD(v27) = 187;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)&dword_18005CAC4,
            v12,
            v13,
            (__int64)v25,
            (__int64)&v27,
            (__int64)&v26);
        }
      }
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2147418113;
      }
      goto LABEL_35;
    }
    _InterlockedIncrement8((volatile signed __int8 *)*v9 + 204);
    if ( (unsigned int)dword_180069000 > 5 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      v26 = 204;
      v27 = "Feedback manager created";
      v25[0] = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        qword_180069018,
        (unsigned int)&dword_18005E76C,
        v21,
        v22,
        (__int64)v25,
        (__int64)&v26,
        (__int64)&v27);
    }
    *a3 = v9;
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_180069000 > 5 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      v26 = 211;
      v27 = "No feedback supported by this device";
      v25[0] = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)v25,
        (unsigned int)byte_18005AC3D,
        v12,
        (_DWORD)v17,
        (__int64)v25,
        (__int64)&v26,
        (__int64)&v27);
    }
    FeedbackManager::~FeedbackManager(v9, v11, v12, (int)v17);
    operator delete(v9, v18);
    return 1;
  }
}

```

## disassembly

```asm
0x180012684  mov     [rsp-28h+arg_0], rbx
0x180012689  push    rbp
0x18001268a  push    rsi
0x18001268b  push    rdi
0x18001268c  push    r14
0x18001268e  push    r15
0x180012690  mov     rbp, rsp
0x180012693  sub     rsp, 50h
0x180012697  mov     r14, rcx
0x18001269a  xor     r15d, r15d
0x18001269d  mov     [r8], r15
0x1800126a0  mov     rsi, r8
0x1800126a3  mov     rcx, gs:60h
0x1800126ac  mov     rbx, rdx
0x1800126af  xor     edx, edx; Flags
0x1800126b1  lea     r8d, [r15+10h]; Size
0x1800126b5  mov     rcx, [rcx+30h]; HeapHandle
0x1800126b9  call    cs:__imp_RtlAllocateHeap
0x1800126c0  nop     dword ptr [rax+rax+00h]
0x1800126c5  mov     rdi, rax
0x1800126c8  test    rax, rax
0x1800126cb  jz      loc_180012A3E
0x1800126d1  mov     [rax], r15
0x1800126d4  xor     edx, edx; Flags
0x1800126d6  mov     [rax+8], r15
0x1800126da  mov     r8d, 0D0h; Size
0x1800126e0  mov     rcx, gs:60h
0x1800126e9  mov     rcx, [rcx+30h]; HeapHandle
0x1800126ed  call    cs:__imp_RtlAllocateHeap
0x1800126f4  nop     dword ptr [rax+rax+00h]
0x1800126f9  test    rax, rax
0x1800126fc  jz      loc_1800129C0
0x180012702  mov     [rax], r15
0x180012705  mov     r8, rbx; struct APP_LOCAL_DEVICE_ID *
0x180012708  mov     [rax+8], r15
0x18001270c  mov     rdx, r14; struct IGameInputServerDevice *
0x18001270f  mov     [rax+10h], r15
0x180012713  mov     rcx, rax; this
0x180012716  mov     [rax+18h], r15
0x18001271a  mov     [rax+20h], r15
0x18001271e  mov     [rax+28h], r15b
0x180012722  mov     [rax+30h], r15
0x180012726  mov     [rax+38h], r15
0x18001272a  mov     [rax+40h], r15
0x18001272e  mov     [rax+48h], r15
0x180012732  mov     [rax+50h], r15
0x180012736  mov     dword ptr [rax+0A8h], 1000000h
0x180012740  mov     byte ptr [rax+0CCh], 1
0x180012747  mov     [rax+58h], r15
0x18001274b  mov     [rax+60h], r15
0x18001274f  mov     [rax+68h], r15
0x180012753  mov     [rax+70h], r15
0x180012757  mov     [rax+78h], r15
0x18001275b  mov     [rax+80h], r15
0x180012762  mov     [rax+88h], r15
0x180012769  mov     [rax+90h], r15
0x180012770  mov     [rax+98h], r15
0x180012777  mov     [rax+0A0h], r15
0x18001277e  mov     [rdi], rax
0x180012781  call    ?Initialize@FeedbackManagerState@@QEAAJPEAUIGameInputServerDevice@@PEBUAPP_LOCAL_DEVICE_ID@@@Z; FeedbackManagerState::Initialize(IGameInputServerDevice *,APP_LOCAL_DEVICE_ID const *)
0x180012786  mov     ebx, eax
0x180012788  test    eax, eax
0x18001278a  jns     short loc_1800127D4
0x18001278c  mov     ecx, cs:dword_180069000
0x180012792  cmp     ecx, 2
0x180012795  jbe     loc_180012A2C
0x18001279b  mov     rdx, cs:qword_180069018
0x1800127a2  mov     rcx, cs:qword_180069010
0x1800127a9  test    cl, 8
0x1800127ac  jz      loc_180012A2C
0x1800127b2  mov     rax, rdx
0x1800127b5  and     eax, 8
0x1800127b8  cmp     rax, rdx
0x1800127bb  jnz     loc_180012A2C
0x1800127c1  mov     dword ptr [rbp+arg_18], 0ABh
0x1800127c8  lea     rdx, byte_18005BD5F
0x1800127cf  jmp     loc_1800129FE
0x1800127d4  mov     r9, [rdi]; lpParameter
0x1800127d7  cmp     [r9+30h], r15d
0x1800127db  jnz     loc_18001287B
0x1800127e1  cmp     [r9+34h], r15d
0x1800127e5  jnz     loc_18001287B
0x1800127eb  cmp     [r9+50h], r15d
0x1800127ef  jnz     loc_18001287B
0x1800127f5  mov     eax, cs:dword_180069000
0x1800127fb  cmp     eax, 5
0x1800127fe  jbe     short loc_180012861
0x180012800  mov     rcx, cs:qword_180069018
0x180012807  mov     rax, cs:qword_180069010
0x18001280e  test    al, 8
0x180012810  jz      short loc_180012861
0x180012812  mov     rax, rcx
0x180012815  and     eax, 8
0x180012818  cmp     rax, rcx
0x18001281b  jnz     short loc_180012861
0x18001281d  lea     rcx, [rbp+arg_18]
0x180012821  mov     [rbp+arg_10], 0D3h
0x180012828  mov     [rsp+50h+var_20], rcx
0x18001282d  lea     rax, aNoFeedbackSupp; "No feedback supported by this device"
0x180012834  lea     rcx, [rbp+arg_10]
0x180012838  mov     [rbp+arg_18], rax
0x18001283c  mov     [rsp+50h+lpThreadId], rcx
0x180012841  lea     rax, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x180012848  lea     rcx, [rbp+var_10]
0x18001284c  mov     [rbp+var_10], rax
0x180012850  lea     rdx, byte_18005AC3D
0x180012857  mov     qword ptr [rsp+50h+dwCreationFlags], rcx
0x18001285c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180012861  mov     rcx, rdi; this
0x180012864  call    ??1FeedbackManager@@QEAA@XZ; FeedbackManager::~FeedbackManager(void)
0x180012869  mov     rcx, rdi; P
0x18001286c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012871  mov     eax, 1
0x180012876  jmp     loc_180012AA9
0x18001287b  mov     [rsp+50h+lpThreadId], r15; lpThreadId
0x180012880  lea     r8, ?WorkerThreadProc@FeedbackManager@@CAKPEAX@Z; lpStartAddress
0x180012887  xor     edx, edx; dwStackSize
0x180012889  mov     [rsp+50h+dwCreationFlags], r15d; dwCreationFlags
0x18001288e  xor     ecx, ecx; lpThreadAttributes
0x180012890  call    cs:__imp_CreateThread
0x180012897  nop     dword ptr [rax+rax+00h]
0x18001289c  mov     [rdi+8], rax
0x1800128a0  test    rax, rax
0x1800128a3  jnz     loc_18001293E
0x1800128a9  call    cs:__imp_GetLastError
0x1800128b0  nop     dword ptr [rax+rax+00h]
0x1800128b5  mov     ecx, cs:dword_180069000
0x1800128bb  mov     ebx, eax
0x1800128bd  cmp     ecx, 2
0x1800128c0  jbe     short loc_18001291C
0x1800128c2  mov     rax, cs:qword_180069018
0x1800128c9  mov     rcx, cs:qword_180069010
0x1800128d0  test    cl, 8
0x1800128d3  jz      short loc_18001291C
0x1800128d5  mov     rcx, rax
0x1800128d8  and     ecx, 8
0x1800128db  cmp     rcx, rax
0x1800128de  jnz     short loc_18001291C
0x1800128e0  lea     rax, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x1800128e7  mov     [rbp+arg_10], ebx
0x1800128ea  mov     [rbp+var_10], rax
0x1800128ee  lea     rdx, dword_18005CAC4
0x1800128f5  lea     rax, [rbp+arg_10]
0x1800128f9  mov     dword ptr [rbp+arg_18], 0BBh
0x180012900  mov     [rsp+50h+var_20], rax
0x180012905  lea     rax, [rbp+arg_18]
0x180012909  mov     [rsp+50h+lpThreadId], rax
0x18001290e  lea     rax, [rbp+var_10]
0x180012912  mov     qword ptr [rsp+50h+dwCreationFlags], rax
0x180012917  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001291c  test    ebx, ebx
0x18001291e  jnz     short loc_18001292A
0x180012920  mov     ebx, 8000FFFFh
0x180012925  jmp     loc_180012A2C
0x18001292a  jle     loc_180012A2C
0x180012930  movzx   ebx, bx
0x180012933  or      ebx, 80070000h
0x180012939  jmp     loc_180012A2C
0x18001293e  mov     rax, [rdi]
0x180012941  nop
0x180012942  lock inc byte ptr [rax+0CCh]
0x180012949  nop
0x18001294a  mov     eax, cs:dword_180069000
0x180012950  cmp     eax, 5
0x180012953  jbe     short loc_1800129B6
0x180012955  mov     rcx, cs:qword_180069018
0x18001295c  mov     rax, cs:qword_180069010
0x180012963  test    al, 8
0x180012965  jz      short loc_1800129B6
0x180012967  mov     rax, rcx
0x18001296a  and     eax, 8
0x18001296d  cmp     rax, rcx
0x180012970  jnz     short loc_1800129B6
0x180012972  lea     rax, aFeedbackManage_0; "Feedback manager created"
0x180012979  mov     [rbp+arg_10], 0CCh
0x180012980  mov     [rbp+arg_18], rax
0x180012984  lea     rdx, dword_18005E76C
0x18001298b  lea     rax, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x180012992  mov     [rbp+var_10], rax
0x180012996  lea     rax, [rbp+arg_18]
0x18001299a  mov     [rsp+50h+var_20], rax
0x18001299f  lea     rax, [rbp+arg_10]
0x1800129a3  mov     [rsp+50h+lpThreadId], rax
0x1800129a8  lea     rax, [rbp+var_10]
0x1800129ac  mov     qword ptr [rsp+50h+dwCreationFlags], rax
0x1800129b1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800129b6  mov     [rsi], rdi
0x1800129b9  xor     eax, eax
0x1800129bb  jmp     loc_180012AA9
0x1800129c0  mov     [rdi], r15
0x1800129c3  mov     ebx, 8007000Eh
0x1800129c8  mov     eax, cs:dword_180069000
0x1800129ce  cmp     eax, 2
0x1800129d1  jbe     short loc_180012A2C
0x1800129d3  mov     rcx, cs:qword_180069018
0x1800129da  mov     rax, cs:qword_180069010
0x1800129e1  test    al, 8
0x1800129e3  jz      short loc_180012A2C
0x1800129e5  mov     rax, rcx
0x1800129e8  and     eax, 8
0x1800129eb  cmp     rax, rcx
0x1800129ee  jnz     short loc_180012A2C
0x1800129f0  mov     dword ptr [rbp+arg_18], 0AAh
0x1800129f7  lea     rdx, word_18005CB7E
0x1800129fe  lea     rax, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x180012a05  mov     [rbp+var_10], rax
0x180012a09  lea     rax, [rbp+arg_10]
0x180012a0d  mov     [rsp+50h+var_20], rax
0x180012a12  lea     rax, [rbp+arg_18]
0x180012a16  mov     [rsp+50h+lpThreadId], rax
0x180012a1b  lea     rax, [rbp+var_10]
0x180012a1f  mov     qword ptr [rsp+50h+dwCreationFlags], rax
0x180012a24  mov     [rbp+arg_10], ebx
0x180012a27  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180012a2c  mov     rcx, rdi; this
0x180012a2f  call    ??1FeedbackManager@@QEAA@XZ; FeedbackManager::~FeedbackManager(void)
0x180012a34  mov     rcx, rdi; P
0x180012a37  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012a3c  jmp     short loc_180012AA7
0x180012a3e  mov     eax, cs:dword_180069000
0x180012a44  mov     ebx, 8007000Eh
0x180012a49  cmp     eax, 2
0x180012a4c  jbe     short loc_180012AA7
0x180012a4e  mov     rcx, cs:qword_180069018
0x180012a55  mov     rax, cs:qword_180069010
0x180012a5c  test    al, 8
0x180012a5e  jz      short loc_180012AA7
0x180012a60  mov     rax, rcx
0x180012a63  and     eax, 8
0x180012a66  cmp     rax, rcx
0x180012a69  jnz     short loc_180012AA7
0x180012a6b  lea     rax, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x180012a72  mov     [rbp+arg_10], ebx
0x180012a75  mov     [rbp+var_10], rax
0x180012a79  lea     rdx, word_18005D062
0x180012a80  lea     rax, [rbp+arg_10]
0x180012a84  mov     dword ptr [rbp+arg_18], 0A5h
0x180012a8b  mov     [rsp+50h+var_20], rax
0x180012a90  lea     rax, [rbp+arg_18]
0x180012a94  mov     [rsp+50h+lpThreadId], rax
0x180012a99  lea     rax, [rbp+var_10]
0x180012a9d  mov     qword ptr [rsp+50h+dwCreationFlags], rax
0x180012aa2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180012aa7  mov     eax, ebx
0x180012aa9  mov     rbx, [rsp+50h+arg_0]
0x180012ab1  add     rsp, 50h
0x180012ab5  pop     r15
0x180012ab7  pop     r14
0x180012ab9  pop     rdi
0x180012aba  pop     rsi
0x180012abb  pop     rbp
0x180012abc  retn
```
