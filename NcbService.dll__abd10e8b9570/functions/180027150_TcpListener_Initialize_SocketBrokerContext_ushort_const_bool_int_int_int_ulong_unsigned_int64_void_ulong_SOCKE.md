# TcpListener::Initialize(SocketBrokerContext *,ushort const *,bool,int,int,int,ulong,unsigned __int64,void *,ulong,_SOCKET_BROKER_APP_CONTEXT *,_SOCKET_BROKER_SSL_CONTEXT *,_DNS_REGISTRATION_DATA *)

- ea: `0x180027150`
- end: `0x1800272bc`
- name: `?Initialize@TcpListener@@UEAAKPEAVSocketBrokerContext@@PEBG_NHHHK_KPEAXKPEAU_SOCKET_BROKER_APP_CONTEXT@@PEAU_SOCKET_BROKER_SSL_CONTEXT@@PEAU_DNS_REGISTRATION_DATA@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(TcpListener *this, struct SocketBrokerContext *, const unsigned __int16 *, char, int, int, int, char vInBuffer, void *, void *, unsigned int, struct _SOCKET_BROKER_APP_CONTEXT *, struct _SOCKET_BROKER_SSL_CONTEXT *, struct _DNS_REGISTRATION_DATA *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000a0a0`
- `0x180012490`
- `0x180027150`
- `0x1800272e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002725d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002725d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027285`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002716b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002716b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800272a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800272a9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18002724b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18002724b`

## string_xrefs

- `0x18002726e`: `TcpListener: CreateThreadpoolIo failed with`

## pseudocode

```c
__int64 __fastcall TcpListener::Initialize(
        TcpListener *this,
        struct SocketBrokerContext *a2,
        const unsigned __int16 *a3,
        char a4,
        int a5,
        int a6,
        int a7,
        char vInBuffer,
        void *a9,
        void *a10,
        unsigned int a11,
        struct _SOCKET_BROKER_APP_CONTEXT *a12,
        struct _SOCKET_BROKER_SSL_CONTEXT *a13,
        struct _DNS_REGISTRATION_DATA *a14)
{
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned int v20; // ebx
  __int64 v21; // r9
  const wchar_t *v22; // r8
  unsigned int LastError; // eax
  PTP_IO ThreadpoolIo; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( a6 == 1 )
  {
    LastError = SharedSocket::Initialize(this, a2, a3, a4, a5, 1, a7, vInBuffer, a9, a10, a11, a12, a13, a14);
    v20 = LastError;
    if ( LastError )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
        goto LABEL_15;
      v22 = L"TcpListener: SharedSocket::Initialize failed with";
    }
    else
    {
      ThreadpoolIo = CreateThreadpoolIo(*((HANDLE *)this + 4), TcpListener::IoCompletionCallback, this, 0);
      *((_QWORD *)this + 104) = ThreadpoolIo;
      if ( ThreadpoolIo )
      {
        v20 = TcpListener::PostAccept(this);
        if ( !v20 )
          goto LABEL_15;
        LastError = GetLastError();
        v20 = LastError;
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
          goto LABEL_15;
        v22 = L"TcpListener: PostAccept failed with";
      }
      else
      {
        LastError = GetLastError();
        v20 = LastError;
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
          goto LABEL_15;
        v22 = L"TcpListener: CreateThreadpoolIo failed with";
      }
    }
    v21 = LastError;
    goto LABEL_14;
  }
  v20 = 87;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v21 = 87;
    v22 = L"TcpListener: invalid socket type passed";
LABEL_14:
    McTemplateU0zq_EventWriteTransfer(v19, v18, v22, v21);
  }
LABEL_15:
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  return v20;
}

```

## disassembly

```asm
0x180027150  push    rbx
0x180027152  push    rbp
0x180027153  push    rsi
0x180027154  push    rdi
0x180027155  push    r14
0x180027157  sub     rsp, 70h
0x18002715b  mov     rdi, rcx
0x18002715e  mov     bl, r9b
0x180027161  add     rcx, 28h ; '('; lpCriticalSection
0x180027165  mov     rbp, r8
0x180027168  mov     r14, rdx
0x18002716b  call    cs:__imp_EnterCriticalSection
0x180027171  cmp     [rsp+98h+arg_28], 1
0x180027179  jz      short loc_18002719C
0x18002717b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027182  mov     ebx, 57h ; 'W'
0x180027187  jz      loc_1800272A5
0x18002718d  mov     r9d, ebx
0x180027190  lea     r8, aTcplistenerInv; "TcpListener: invalid socket type passed"
0x180027197  jmp     loc_1800272A0
0x18002719c  mov     rax, [rsp+98h+arg_68]
0x1800271a4  mov     r9b, bl; bool
0x1800271a7  mov     [rsp+98h+var_30], rax; struct _DNS_REGISTRATION_DATA *
0x1800271ac  mov     r8, rbp; unsigned __int16 *
0x1800271af  mov     rax, [rsp+98h+arg_60]
0x1800271b7  mov     rdx, r14; struct SocketBrokerContext *
0x1800271ba  mov     [rsp+98h+var_38], rax; struct _SOCKET_BROKER_SSL_CONTEXT *
0x1800271bf  mov     rcx, rdi; this
0x1800271c2  mov     rax, [rsp+98h+arg_58]
0x1800271ca  mov     [rsp+98h+var_40], rax; struct _SOCKET_BROKER_APP_CONTEXT *
0x1800271cf  mov     eax, [rsp+98h+arg_50]
0x1800271d6  mov     [rsp+98h+var_48], eax; unsigned int
0x1800271da  mov     rax, [rsp+98h+arg_48]
0x1800271e2  mov     [rsp+98h+var_50], rax; void *
0x1800271e7  mov     rax, [rsp+98h+arg_40]
0x1800271ef  mov     [rsp+98h+var_58], rax; unsigned __int64
0x1800271f4  mov     eax, dword ptr [rsp+98h+arg_38]
0x1800271fb  mov     dword ptr [rsp+98h+vInBuffer], eax; vInBuffer
0x1800271ff  mov     eax, [rsp+98h+arg_30]
0x180027206  mov     [rsp+98h+var_68], eax; int
0x18002720a  mov     eax, [rsp+98h+arg_20]
0x180027211  mov     [rsp+98h+var_70], 1; int
0x180027219  mov     [rsp+98h+var_78], eax; int
0x18002721d  call    ?Initialize@SharedSocket@@UEAAKPEAVSocketBrokerContext@@PEBG_NHHHK_KPEAXKPEAU_SOCKET_BROKER_APP_CONTEXT@@PEAU_SOCKET_BROKER_SSL_CONTEXT@@PEAU_DNS_REGISTRATION_DATA@@@Z; SharedSocket::Initialize(SocketBrokerContext *,ushort const *,bool,int,int,int,ulong,unsigned __int64,void *,ulong,_SOCKET_BROKER_APP_CONTEXT *,_SOCKET_BROKER_SSL_CONTEXT *,_DNS_REGISTRATION_DATA *)
0x180027222  mov     ebx, eax
0x180027224  test    eax, eax
0x180027226  jz      short loc_18002723A
0x180027228  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18002722f  jz      short loc_1800272A5
0x180027231  lea     r8, aTcplistenerSha; "TcpListener: SharedSocket::Initialize f"...
0x180027238  jmp     short loc_18002729D
0x18002723a  mov     rcx, [rdi+20h]; fl
0x18002723e  lea     rdx, ?IoCompletionCallback@TcpListener@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x180027245  xor     r9d, r9d; pcbe
0x180027248  mov     r8, rdi; pv
0x18002724b  call    cs:__imp_CreateThreadpoolIo
0x180027251  mov     [rdi+340h], rax
0x180027258  test    rax, rax
0x18002725b  jnz     short loc_180027277
0x18002725d  call    cs:__imp_GetLastError
0x180027263  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18002726a  mov     ebx, eax
0x18002726c  jz      short loc_1800272A5
0x18002726e  lea     r8, aTcplistenerCre; "TcpListener: CreateThreadpoolIo failed "...
0x180027275  jmp     short loc_18002729D
0x180027277  mov     rcx, rdi; this
0x18002727a  call    ?PostAccept@TcpListener@@AEAAKXZ; TcpListener::PostAccept(void)
0x18002727f  mov     ebx, eax
0x180027281  test    eax, eax
0x180027283  jz      short loc_1800272A5
0x180027285  call    cs:__imp_GetLastError
0x18002728b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027292  mov     ebx, eax
0x180027294  jz      short loc_1800272A5
0x180027296  lea     r8, aTcplistenerPos; "TcpListener: PostAccept failed with"
0x18002729d  mov     r9d, eax
0x1800272a0  call    McTemplateU0zq_EventWriteTransfer
0x1800272a5  lea     rcx, [rdi+28h]; lpCriticalSection
0x1800272a9  call    cs:__imp_LeaveCriticalSection
0x1800272af  mov     eax, ebx
0x1800272b1  add     rsp, 70h
0x1800272b5  pop     r14
0x1800272b7  pop     rdi
0x1800272b8  pop     rsi
0x1800272b9  pop     rbp
0x1800272ba  pop     rbx
0x1800272bb  retn
```
