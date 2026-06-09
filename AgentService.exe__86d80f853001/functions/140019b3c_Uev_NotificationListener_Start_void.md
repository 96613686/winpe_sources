# Uev::NotificationListener::Start(void)

- ea: `0x140019b3c`
- end: `0x140019f84`
- name: `?Start@NotificationListener@Uev@@QEAAJXZ`
- size: `1096`
- prototype: `__int64 __fastcall(Uev::NotificationListener *this, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000b2e0`

## callees

- `0x140003e50`
- `0x140004a54`
- `0x140004a78`
- `0x140004ab4`
- `0x140004b14`
- `0x14000ac58`
- `0x14000ac88`
- `0x14000acc4`
- `0x14000d1d8`
- `0x14000d260`
- `0x1400191ec`
- `0x140019244`
- `0x1400192c0`
- `0x140019438`
- `0x14001954c`
- `0x140019b3c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140019ed3`
- `KERNEL32!CloseHandle` at `0x140019ed3`
- `KERNEL32!CreateThread` at `0x140019d2e`
- `KERNEL32!CreateThread` at `0x140019d2e`
- `KERNEL32!GetLastError` at `0x140019d4a`
- `KERNEL32!GetLastError` at `0x140019edf`
- `KERNEL32!GetLastError` at `0x140019d4a`
- `KERNEL32!GetLastError` at `0x140019edf`
- `KERNEL32!CreateIoCompletionPort` at `0x140019c3f`
- `KERNEL32!CreateIoCompletionPort` at `0x140019c3f`
- `KERNEL32!GetSystemInfo` at `0x140019c18`
- `KERNEL32!GetSystemInfo` at `0x140019c18`
- `FLTLIB!FilterConnectCommunicationPort` at `0x140019bd5`
- `FLTLIB!FilterConnectCommunicationPort` at `0x140019bd5`

## string_xrefs

- `0x140019f51`: `Attempting to use an invalid handle.`
- `0x140019b91`: `AgentService.FilterConnection::Initialize: Entry`
- `0x140019be3`: `AgentService.FilterConnection::Initialize: Failed to connect, status = 0x%X`
- `0x140019bf1`: `AgentService.FilterConnection::Initialize: Exit, retStatus = 0x%X`
- `0x140019b77`: `AgentService.NotificationListener::Start: Entry`
- `0x140019d5e`: `AgentService.NotificationListener:: Failed to create thread, status = 0x%X`
- `0x140019ea2`: `AgentService.NotificationListener:: Failed to post receive message, status = 0x%X`
- `0x140019ef4`: `AgentService.NotificationListener:: Failed to open completion port, status = 0x%X`
- `0x140019efd`: `AgentService.NotificationListener:: Filter connection initialized failed, status = 0x%X`
- `0x140019f0e`: `AgentService.NotificationListener::Start: Exit, retStatus = 0x%X`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Uev::NotificationListener::Start(Uev::NotificationListener *this, __int64 a2)
{
  char *v2; // rdi
  int v3; // r12d
  HANDLE *v4; // r13
  int v5; // ebx
  const WCHAR *v6; // rcx
  __int64 v7; // r15
  HANDLE IoCompletionPort; // rax
  _QWORD *v9; // r14
  __int64 v10; // rdx
  char *v11; // rsi
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rbx
  size_t v14; // rbx
  unsigned int i; // ebx
  int v16; // r15d
  __int64 v17; // rdx
  __int64 v18; // r14
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // r14
  unsigned __int64 v24; // rcx
  size_t v25; // rax
  size_t v26; // rbx
  __int64 v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rax
  signed int LastError; // eax
  wchar_t *v31; // rcx
  __int64 v32; // rdx
  __int64 Buf1; // [rsp+30h] [rbp-D0h] BYREF
  __int64 Buf2; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v36[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp-A0h] BYREF
  int Context; // [rsp+A0h] [rbp-60h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Buffer[256]; // [rsp+E0h] [rbp-20h] BYREF

  v2 = (char *)pCreateProcNotificationListener;
  v3 = 0;
  DbgTrace<4>(L"AgentService.NotificationListener::Start: Entry", a2);
  Context = 1;
  v4 = (HANDLE *)(v2 + 152);
  DbgTrace<5>(L"AgentService.FilterConnection::Initialize: Entry");
  if ( (unsigned __int64)(*((_QWORD *)v2 + 19) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v6 = (const WCHAR *)(v2 + 112);
    if ( *((_QWORD *)v2 + 17) > 7u )
      v6 = *(const WCHAR **)v6;
    v5 = FilterConnectCommunicationPort(v6, 0, &Context, 4u, 0, (HANDLE *)v2 + 19);
    if ( v5 < 0 )
      DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.FilterConnection::Initialize: Failed to connect, status = 0x%X");
  }
  else
  {
    v5 = -2147024713;
  }
  DbgTraceFrmt<5,long>((wchar_t *)L"AgentService.FilterConnection::Initialize: Exit, retStatus = 0x%X");
  if ( v5 < 0 )
  {
    v31 = (wchar_t *)L"AgentService.NotificationListener:: Filter connection initialized failed, status = 0x%X";
LABEL_54:
    DbgTraceFrmtErr<long>(v31);
    goto LABEL_55;
  }
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  if ( (char *)*v4 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    std::wstring::wstring(v36, L"Attempting to use an invalid handle.");
    Uev::SmartHandleException::SmartHandleException(pExceptionObject, v36);
    throw (Uev::SmartHandleException *)pExceptionObject;
  }
  v7 = 2 * SystemInfo.dwNumberOfProcessors;
  IoCompletionPort = CreateIoCompletionPort(*v4, 0, 0, 2 * SystemInfo.dwNumberOfProcessors);
  *((_QWORD *)v2 + 1) = IoCompletionPort;
  if ( !IoCompletionPort )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v31 = L"AgentService.NotificationListener:: Failed to open completion port, status = 0x%X";
    goto LABEL_54;
  }
  *((_DWORD *)v2 + 4) = *((_DWORD *)v2 + 26) + 16;
  v9 = v2 + 24;
  Buf1 = 0;
  v10 = *((_QWORD *)v2 + 3);
  v11 = (char *)*((_QWORD *)v2 + 4);
  v12 = (__int64)&v11[-v10] >> 3;
  if ( (unsigned int)v7 >= v12 )
  {
    if ( (unsigned int)v7 > v12 )
    {
      if ( (unsigned int)v7 <= (unsigned __int64)((*((_QWORD *)v2 + 5) - v10) >> 3) )
      {
        v13 = (unsigned int)v7 - v12;
        Buf2 = 0;
        if ( !memcmp_0(&Buf1, &Buf2, 8u) )
        {
          v14 = 8 * v13;
          memset_0(v11, 0, v14);
          v11 += v14;
        }
        else if ( v13 )
        {
          memset_0(v11, 0, 8 * v13);
          do
          {
            v11 += 8;
            --v13;
          }
          while ( v13 );
        }
        *((_QWORD *)v2 + 4) = v11;
      }
      else
      {
        std::vector<void *>::_Resize_reallocate<void *>(v2 + 24, (unsigned int)v7, &Buf1);
      }
    }
  }
  else
  {
    *((_QWORD *)v2 + 4) = v10 + 8 * v7;
  }
  v2[20] = 1;
  for ( i = 0; i < (unsigned int)v7; ++i )
  {
    _InterlockedIncrement((volatile signed __int32 *)v2 + 12);
    *(_QWORD *)(*v9 + 8LL * i) = CreateThread(0, 0, Uev::NotificationListener::ListeningThread, v2, 0, 0);
    if ( !*(_QWORD *)(*v9 + 8LL * i) )
    {
      _InterlockedDecrement((volatile signed __int32 *)v2 + 12);
      GetLastError();
      DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.NotificationListener:: Failed to create thread, status = 0x%X");
    }
  }
  if ( !*((_DWORD *)v2 + 12) )
    goto LABEL_49;
  v16 = 5 * v7;
  v17 = *((_QWORD *)v2 + 7);
  v18 = *((_QWORD *)v2 + 8);
  v19 = 0xCCCCCCCCCCCCCCCDuLL * ((v18 - v17) >> 3);
  if ( v16 >= v19 )
  {
    if ( v16 > v19 )
    {
      if ( v16 <= 0xCCCCCCCCCCCCCCCDuLL * ((*((_QWORD *)v2 + 9) - v17) >> 3) )
      {
        v20 = v16 - v19;
        if ( v20 )
        {
          LOBYTE(v17) = 0;
          memset_0(*((void **)v2 + 8), v17, 40 * v20);
          do
          {
            v18 += 40;
            --v20;
          }
          while ( v20 );
        }
        *((_QWORD *)v2 + 8) = v18;
      }
      else
      {
        std::vector<Uev::_RcvMsgDispatcher>::_Resize_reallocate<std::_Value_init_tag>(v2 + 56, v16);
      }
    }
  }
  else
  {
    *((_QWORD *)v2 + 8) = v17 + 40LL * v16;
  }
  v21 = (unsigned int)(*((_DWORD *)v2 + 4) * v16);
  v22 = *((_QWORD *)v2 + 10);
  v23 = *((_QWORD *)v2 + 11);
  v24 = v23 - v22;
  if ( v21 < v23 - v22 )
  {
    v25 = v22 + (unsigned int)(*((_DWORD *)v2 + 4) * v16);
LABEL_41:
    *((_QWORD *)v2 + 11) = v25;
    goto LABEL_42;
  }
  if ( v21 > v24 )
  {
    if ( v21 <= *((_QWORD *)v2 + 12) - v22 )
    {
      v26 = v21 - v24;
      memset_0(*((void **)v2 + 11), 0, v26);
      v25 = v26 + v23;
      goto LABEL_41;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(
      v2 + 80,
      (unsigned int)(*((_DWORD *)v2 + 4) * v16));
  }
LABEL_42:
  v27 = 0;
  if ( v16 <= 0 )
    goto LABEL_49;
  do
  {
    v28 = 5 * v27;
    v29 = *((_QWORD *)v2 + 7);
    *(_OWORD *)(v29 + 8 * v28 + 8) = 0;
    *(_OWORD *)(v29 + 8 * v28 + 24) = 0;
    *(_DWORD *)(*((_QWORD *)v2 + 7) + 8 * v28) = v27;
    if ( Uev::FilterConnection::PostReceiveBuffer(
           (Uev::FilterConnection *)(v2 + 152),
           (struct _FILTER_MESSAGE_HEADER *const)(*((_QWORD *)v2 + 10) + (unsigned int)(v27 * *((_DWORD *)v2 + 4))),
           *((_DWORD *)v2 + 4),
           (struct _OVERLAPPED *)(*((_QWORD *)v2 + 7) + 8 * (5 * v27 + 1))) == -2147023899 )
      ++v3;
    else
      DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.NotificationListener:: Failed to post receive message, status = 0x%X");
    v27 = (unsigned int)(v27 + 1);
  }
  while ( (int)v27 < v16 );
  if ( !v3 )
  {
LABEL_49:
    v5 = -2147467259;
    v2[20] = 0;
    CloseHandle(*((HANDLE *)v2 + 1));
    *((_QWORD *)v2 + 1) = 0;
    goto LABEL_55;
  }
  v5 = 0;
LABEL_55:
  swprintf_s(Buffer, 0x100u, L"AgentService.NotificationListener::Start: Exit, retStatus = 0x%X", (unsigned int)v5);
  DbgTrace<4>(Buffer, v32);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140019b3c  push    rbp
0x140019b3e  push    rbx
0x140019b3f  push    rsi
0x140019b40  push    rdi
0x140019b41  push    r12
0x140019b43  push    r13
0x140019b45  push    r14
0x140019b47  push    r15
0x140019b49  lea     rbp, [rsp-1F8h]
0x140019b51  sub     rsp, 2F8h
0x140019b58  mov     rax, cs:__security_cookie
0x140019b5f  xor     rax, rsp
0x140019b62  mov     [rbp+230h+var_50], rax
0x140019b69  mov     rdi, cs:?pCreateProcNotificationListener@@3PEAVCreateProcNotificationListener@Uev@@EA; Uev::CreateProcNotificationListener * pCreateProcNotificationListener
0x140019b70  xor     r12d, r12d
0x140019b73  mov     [rbp+230h+Context], r12d
0x140019b77  lea     rcx, aAgentserviceNo_5; "AgentService.NotificationListener::Star"...
0x140019b7e  call    ??$DbgTrace@$03@@YAXPEB_W@Z; DbgTrace<4>(wchar_t const *)
0x140019b83  mov     [rbp+230h+Context], 1
0x140019b8a  lea     r13, [rdi+98h]
0x140019b91  lea     rcx, aAgentserviceFi_1; "AgentService.FilterConnection::Initiali"...
0x140019b98  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x140019b9d  mov     rax, [r13+0]
0x140019ba1  dec     rax
0x140019ba4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019ba8  ja      short loc_140019BB1
0x140019baa  mov     ebx, 800700B7h
0x140019baf  jmp     short loc_140019BEF
0x140019bb1  lea     rcx, [rdi+70h]
0x140019bb5  cmp     qword ptr [rcx+18h], 7
0x140019bba  jbe     short loc_140019BBF
0x140019bbc  mov     rcx, [rcx]; lpPortName
0x140019bbf  mov     r9d, 4; wSizeOfContext
0x140019bc5  mov     [rsp+330h+hPort], r13; hPort
0x140019bca  mov     [rsp+330h+lpSecurityAttributes], r12; lpSecurityAttributes
0x140019bcf  lea     r8, [rbp+230h+Context]; lpContext
0x140019bd3  xor     edx, edx; dwOptions
0x140019bd5  call    cs:__imp_FilterConnectCommunicationPort
0x140019bdb  mov     ebx, eax
0x140019bdd  test    eax, eax
0x140019bdf  jns     short loc_140019BEF
0x140019be1  mov     edx, eax
0x140019be3  lea     rcx, aAgentserviceFi_8; "AgentService.FilterConnection::Initiali"...
0x140019bea  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x140019bef  mov     edx, ebx
0x140019bf1  lea     rcx, aAgentserviceFi_6; "AgentService.FilterConnection::Initiali"...
0x140019bf8  call    ??$DbgTraceFrmt@$04J@@YAXPEB_WJ@Z; DbgTraceFrmt<5,long>(wchar_t const *,long)
0x140019bfd  test    ebx, ebx
0x140019bff  js      loc_140019EFD
0x140019c05  xorps   xmm0, xmm0
0x140019c08  movups  xmmword ptr [rbp+230h+SystemInfo], xmm0
0x140019c0c  movups  xmmword ptr [rbp+230h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x140019c10  movups  xmmword ptr [rbp+230h+SystemInfo.dwNumberOfProcessors], xmm0
0x140019c14  lea     rcx, [rbp+230h+SystemInfo]; lpSystemInfo
0x140019c18  call    cs:__imp_GetSystemInfo
0x140019c1e  mov     rcx, [r13+0]; FileHandle
0x140019c22  lea     rax, [rcx-1]
0x140019c26  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019c2a  ja      loc_140019F51
0x140019c30  mov     eax, [rbp+230h+SystemInfo.dwNumberOfProcessors]
0x140019c33  lea     r15d, [rax+rax]
0x140019c37  mov     r9d, r15d; NumberOfConcurrentThreads
0x140019c3a  xor     r8d, r8d; CompletionKey
0x140019c3d  xor     edx, edx; ExistingCompletionPort
0x140019c3f  call    cs:__imp_CreateIoCompletionPort
0x140019c45  mov     [rdi+8], rax
0x140019c49  test    rax, rax
0x140019c4c  jz      loc_140019EDF
0x140019c52  mov     eax, [rdi+68h]
0x140019c55  add     eax, 10h
0x140019c58  mov     [rdi+10h], eax
0x140019c5b  lea     r14, [rdi+18h]
0x140019c5f  mov     [rsp+330h+Buf1], r12
0x140019c64  mov     rdx, [r14]
0x140019c67  mov     rsi, [r14+8]
0x140019c6b  mov     rcx, rsi
0x140019c6e  sub     rcx, rdx
0x140019c71  sar     rcx, 3
0x140019c75  mov     ebx, r15d
0x140019c78  cmp     rbx, rcx
0x140019c7b  jnb     short loc_140019C87
0x140019c7d  lea     rax, [rdx+r15*8]
0x140019c81  mov     [r14+8], rax
0x140019c85  jmp     short loc_140019D06
0x140019c87  jbe     short loc_140019D06
0x140019c89  mov     rax, [r14+10h]
0x140019c8d  sub     rax, rdx
0x140019c90  sar     rax, 3
0x140019c94  cmp     rbx, rax
0x140019c97  jbe     short loc_140019CAB
0x140019c99  lea     r8, [rsp+330h+Buf1]
0x140019c9e  mov     rdx, rbx
0x140019ca1  mov     rcx, r14
0x140019ca4  call    ??$_Resize_reallocate@PEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAX_KAEBQEAX@Z; std::vector<void *>::_Resize_reallocate<void *>(unsigned __int64,void * const &)
0x140019ca9  jmp     short loc_140019D06
0x140019cab  sub     rbx, rcx
0x140019cae  mov     [rsp+330h+Buf2], r12
0x140019cb3  mov     r8d, 8; Size
0x140019cb9  lea     rdx, [rsp+330h+Buf2]; Buf2
0x140019cbe  lea     rcx, [rsp+330h+Buf1]; Buf1
0x140019cc3  call    memcmp_0
0x140019cc8  test    eax, eax
0x140019cca  jnz     short loc_140019CE2
0x140019ccc  shl     rbx, 3
0x140019cd0  mov     r8, rbx; Size
0x140019cd3  xor     edx, edx; Val
0x140019cd5  mov     rcx, rsi; void *
0x140019cd8  call    memset_0
0x140019cdd  add     rsi, rbx
0x140019ce0  jmp     short loc_140019D02
0x140019ce2  test    rbx, rbx
0x140019ce5  jz      short loc_140019D02
0x140019ce7  mov     r8, rbx
0x140019cea  shl     r8, 3; Size
0x140019cee  xor     edx, edx; Val
0x140019cf0  mov     rcx, rsi; void *
0x140019cf3  call    memset_0
0x140019cf8  add     rsi, 8
0x140019cfc  sub     rbx, 1
0x140019d00  jnz     short loc_140019CF8
0x140019d02  mov     [r14+8], rsi
0x140019d06  mov     byte ptr [rdi+14h], 1
0x140019d0a  mov     ebx, r12d
0x140019d0d  test    r15d, r15d
0x140019d10  jz      short loc_140019D71
0x140019d12  lock inc dword ptr [rdi+30h]
0x140019d16  mov     [rsp+330h+hPort], r12; lpThreadId
0x140019d1b  mov     dword ptr [rsp+330h+lpSecurityAttributes], r12d; dwCreationFlags
0x140019d20  mov     r9, rdi; lpParameter
0x140019d23  lea     r8, ?ListeningThread@NotificationListener@Uev@@CAKPEAX@Z; lpStartAddress
0x140019d2a  xor     edx, edx; dwStackSize
0x140019d2c  xor     ecx, ecx; lpThreadAttributes
0x140019d2e  call    cs:__imp_CreateThread
0x140019d34  mov     edx, ebx
0x140019d36  mov     rcx, [r14]
0x140019d39  mov     [rcx+rdx*8], rax
0x140019d3d  mov     rax, [r14]
0x140019d40  cmp     [rax+rdx*8], r12
0x140019d44  jnz     short loc_140019D6A
0x140019d46  lock dec dword ptr [rdi+30h]
0x140019d4a  call    cs:__imp_GetLastError
0x140019d50  test    eax, eax
0x140019d52  jle     short loc_140019D5C
0x140019d54  movzx   eax, ax
0x140019d57  or      eax, 80070000h
0x140019d5c  mov     edx, eax
0x140019d5e  lea     rcx, aAgentserviceNo_10; "AgentService.NotificationListener:: Fai"...
0x140019d65  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x140019d6a  inc     ebx
0x140019d6c  cmp     ebx, r15d
0x140019d6f  jb      short loc_140019D12
0x140019d71  cmp     [rdi+30h], r12d
0x140019d75  jz      loc_140019EC6
0x140019d7b  lea     r15d, [r15+r15*4]
0x140019d7f  movsxd  rbx, r15d
0x140019d82  mov     rdx, [rdi+38h]
0x140019d86  mov     r14, [rdi+40h]
0x140019d8a  mov     rcx, r14
0x140019d8d  sub     rcx, rdx
0x140019d90  sar     rcx, 3
0x140019d94  mov     r8, 0CCCCCCCCCCCCCCCDh
0x140019d9e  imul    rcx, r8
0x140019da2  cmp     rbx, rcx
0x140019da5  jnb     short loc_140019DB5
0x140019da7  lea     rax, [rbx+rbx*4]
0x140019dab  lea     rcx, [rdx+rax*8]
0x140019daf  mov     [rdi+40h], rcx
0x140019db3  jmp     short loc_140019DFE
0x140019db5  jbe     short loc_140019DFE
0x140019db7  mov     rax, [rdi+48h]
0x140019dbb  sub     rax, rdx
0x140019dbe  sar     rax, 3
0x140019dc2  imul    rax, r8
0x140019dc6  cmp     rbx, rax
0x140019dc9  jbe     short loc_140019DD9
0x140019dcb  mov     rdx, rbx
0x140019dce  lea     rcx, [rdi+38h]
0x140019dd2  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@U_RcvMsgDispatcher@Uev@@V?$allocator@U_RcvMsgDispatcher@Uev@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Uev::_RcvMsgDispatcher>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140019dd7  jmp     short loc_140019DFE
0x140019dd9  sub     rbx, rcx
0x140019ddc  jz      short loc_140019DFA
0x140019dde  lea     r8, [rbx+rbx*4]
0x140019de2  shl     r8, 3; Size
0x140019de6  xor     dl, dl; Val
0x140019de8  mov     rcx, r14; void *
0x140019deb  call    memset_0
0x140019df0  add     r14, 28h ; '('
0x140019df4  sub     rbx, 1
0x140019df8  jnz     short loc_140019DF0
0x140019dfa  mov     [rdi+40h], r14
0x140019dfe  lea     rsi, [rdi+50h]
0x140019e02  mov     eax, r15d
0x140019e05  imul    eax, [rdi+10h]
0x140019e09  mov     ebx, eax
0x140019e0b  mov     rdx, [rsi]
0x140019e0e  mov     r14, [rsi+8]
0x140019e12  mov     rcx, r14
0x140019e15  sub     rcx, rdx
0x140019e18  cmp     rbx, rcx
0x140019e1b  jnb     short loc_140019E22
0x140019e1d  add     rax, rdx
0x140019e20  jmp     short loc_140019E51
0x140019e22  jbe     short loc_140019E55
0x140019e24  mov     rax, [rsi+10h]
0x140019e28  sub     rax, rdx
0x140019e2b  cmp     rbx, rax
0x140019e2e  jbe     short loc_140019E3D
0x140019e30  mov     rdx, rbx
0x140019e33  mov     rcx, rsi
0x140019e36  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140019e3b  jmp     short loc_140019E55
0x140019e3d  sub     rbx, rcx
0x140019e40  mov     r8, rbx; Size
0x140019e43  xor     edx, edx; Val
0x140019e45  mov     rcx, r14; void *
0x140019e48  call    memset_0
0x140019e4d  lea     rax, [rbx+r14]
0x140019e51  mov     [rsi+8], rax
0x140019e55  xor     ebx, ebx
0x140019e57  test    r15d, r15d
0x140019e5a  jle     short loc_140019EC6
0x140019e5c  lea     rcx, [rbx+rbx*4]
0x140019e60  mov     rax, [rdi+38h]
0x140019e64  xorps   xmm0, xmm0
0x140019e67  movups  xmmword ptr [rax+rcx*8+8], xmm0
0x140019e6c  movups  xmmword ptr [rax+rcx*8+18h], xmm0
0x140019e71  mov     rax, [rdi+38h]
0x140019e75  mov     [rax+rcx*8], ebx
0x140019e78  mov     r8d, [rdi+10h]; unsigned int
0x140019e7c  mov     rax, [rdi+38h]
0x140019e80  lea     rcx, [rcx+1]
0x140019e84  lea     r9, [rax+rcx*8]; struct _OVERLAPPED *
0x140019e88  mov     edx, r8d
0x140019e8b  imul    edx, ebx
0x140019e8e  add     rdx, [rsi]; struct _FILTER_MESSAGE_HEADER *
0x140019e91  mov     rcx, r13; this
0x140019e94  call    ?PostReceiveBuffer@FilterConnection@Uev@@QEAAJQEAU_FILTER_MESSAGE_HEADER@@KPEAU_OVERLAPPED@@@Z; Uev::FilterConnection::PostReceiveBuffer(_FILTER_MESSAGE_HEADER * const,ulong,_OVERLAPPED *)
0x140019e99  cmp     eax, 800703E5h
0x140019e9e  jz      short loc_140019EB0
0x140019ea0  mov     edx, eax
0x140019ea2  lea     rcx, aAgentserviceNo_9; "AgentService.NotificationListener:: Fai"...
0x140019ea9  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x140019eae  jmp     short loc_140019EB3
0x140019eb0  inc     r12d
0x140019eb3  inc     ebx
0x140019eb5  cmp     ebx, r15d
0x140019eb8  jl      short loc_140019E5C
0x140019eba  test    r12d, r12d
0x140019ebd  jz      short loc_140019EC3
0x140019ebf  xor     ebx, ebx
0x140019ec1  jmp     short loc_140019F0B
0x140019ec3  xor     r12d, r12d
0x140019ec6  mov     ebx, 80004005h
0x140019ecb  mov     [rdi+14h], r12b
0x140019ecf  mov     rcx, [rdi+8]; hObject
0x140019ed3  call    cs:__imp_CloseHandle
0x140019ed9  mov     [rdi+8], r12
0x140019edd  jmp     short loc_140019F0B
0x140019edf  call    cs:__imp_GetLastError
0x140019ee5  mov     ebx, eax
0x140019ee7  test    eax, eax
0x140019ee9  jle     short loc_140019EF4
0x140019eeb  movzx   ebx, ax
0x140019eee  or      ebx, 80070000h
0x140019ef4  lea     rcx, aAgentserviceNo_3; "AgentService.NotificationListener:: Fai"...
0x140019efb  jmp     short loc_140019F04
0x140019efd  lea     rcx, aAgentserviceNo; "AgentService.NotificationListener:: Fil"...
0x140019f04  mov     edx, ebx
0x140019f06  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x140019f0b  mov     r9d, ebx
0x140019f0e  lea     r8, aAgentserviceNo_0; "AgentService.NotificationListener::Star"...
0x140019f15  mov     edx, 100h; BufferCount
0x140019f1a  lea     rcx, [rbp+230h+Buffer]; Buffer
0x140019f1e  call    swprintf_s
0x140019f23  lea     rcx, [rbp+230h+Buffer]
0x140019f27  call    ??$DbgTrace@$03@@YAXPEB_W@Z; DbgTrace<4>(wchar_t const *)
0x140019f2c  mov     eax, ebx
0x140019f2e  mov     rcx, [rbp+230h+var_50]
0x140019f35  xor     rcx, rsp; StackCookie
0x140019f38  call    __security_check_cookie
0x140019f3d  add     rsp, 2F8h
0x140019f44  pop     r15
0x140019f46  pop     r14
0x140019f48  pop     r13
0x140019f4a  pop     r12
0x140019f4c  pop     rdi
0x140019f4d  pop     rsi
0x140019f4e  pop     rbx
0x140019f4f  pop     rbp
0x140019f50  retn
0x140019f51  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x140019f58  lea     rcx, [rsp+330h+var_2F0]
0x140019f5d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140019f62  nop
0x140019f63  lea     rdx, [rsp+330h+var_2F0]
0x140019f68  lea     rcx, [rsp+330h+pExceptionObject]
0x140019f6d  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x140019f72  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x140019f79  lea     rcx, [rsp+330h+pExceptionObject]; pExceptionObject
0x140019f7e  call    _CxxThrowException_0
  ... truncated ...
```
