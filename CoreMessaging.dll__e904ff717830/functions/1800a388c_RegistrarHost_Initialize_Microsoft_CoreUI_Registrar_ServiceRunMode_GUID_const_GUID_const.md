# RegistrarHost::Initialize(Microsoft::CoreUI::Registrar::ServiceRunMode,_GUID const *,_GUID const *)

- ea: `0x1800a388c`
- end: `0x1800a39ff`
- name: `?Initialize@RegistrarHost@@IEAAXW4ServiceRunMode@Registrar@CoreUI@Microsoft@@PEBU_GUID@@1@Z`
- size: `371`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a2c50`
- `0x1800a37a4`

## callees

- `0x180007d80`
- `0x18003950c`
- `0x18008cc78`
- `0x18009d670`
- `0x1800a388c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a38cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a3909`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a38cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a3909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a38de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a38de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3968`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800a3956`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800a3956`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a39de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a39de`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800a39a5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800a39a5`

## pseudocode

```c
BOOL __fastcall RegistrarHost::Initialize(__int64 a1, int a2, _OWORD *a3, _OWORD *a4)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v7; // rax
  signed int v8; // eax
  HANDLE Thread; // rax
  void *v10; // rcx
  signed int v11; // eax
  void *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r8
  BOOL result; // eax
  HANDLE Handles[2]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v17[16]; // [rsp+40h] [rbp-28h] BYREF

  *(_DWORD *)(a1 + 8) = a2;
  if ( a3 )
    *(_OWORD *)(a1 + 12) = *a3;
  if ( a4 )
    *(_OWORD *)(a1 + 28) = *a4;
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(a1 + 56) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CFlat::Abandonment::FailWithHR(LastError, 0, 0);
  }
  v7 = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(a1 + 64) = v7;
  if ( !v7 )
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    CFlat::Abandonment::FailWithHR(v8, 0, 0);
  }
  Thread = CreateThread(0, 0, RegistrarHost::RegistrarThreadProc, (LPVOID)a1, 0, 0);
  *(_QWORD *)(a1 + 48) = Thread;
  v10 = Thread;
  if ( !Thread )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    CFlat::Abandonment::FailWithHR(v11, 0, 0);
  }
  v12 = *(void **)(a1 + 56);
  Handles[1] = v10;
  Handles[0] = v12;
  if ( WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) )
    CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode();
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v13, CoreUIService_InitializeService, v14, 1, v17);
  result = CloseHandle(*(HANDLE *)(a1 + 56));
  *(_QWORD *)(a1 + 56) = 0;
  return result;
}

```

## disassembly

```asm
0x1800a388c  push    rbx
0x1800a388e  sub     rsp, 60h
0x1800a3892  mov     rax, cs:__security_cookie
0x1800a3899  xor     rax, rsp
0x1800a389c  mov     [rsp+68h+var_18], rax
0x1800a38a1  mov     [rcx+8], edx
0x1800a38a4  mov     rbx, rcx
0x1800a38a7  test    r8, r8
0x1800a38aa  jz      short loc_1800A38B5
0x1800a38ac  movups  xmm0, xmmword ptr [r8]
0x1800a38b0  movdqu  xmmword ptr [rcx+0Ch], xmm0
0x1800a38b5  test    r9, r9
0x1800a38b8  jz      short loc_1800A38C3
0x1800a38ba  movups  xmm0, xmmword ptr [r9]
0x1800a38be  movdqu  xmmword ptr [rcx+1Ch], xmm0
0x1800a38c3  xor     r9d, r9d; lpName
0x1800a38c6  xor     r8d, r8d; bInitialState
0x1800a38c9  xor     ecx, ecx; lpEventAttributes
0x1800a38cb  lea     edx, [r9+1]; bManualReset
0x1800a38cf  call    cs:__imp_CreateEventW
0x1800a38d5  mov     [rbx+38h], rax
0x1800a38d9  test    rax, rax
0x1800a38dc  jnz     short loc_1800A38FD
0x1800a38de  call    cs:__imp_GetLastError
0x1800a38e4  test    eax, eax
0x1800a38e6  jle     short loc_1800A38F0
0x1800a38e8  movzx   eax, ax
0x1800a38eb  or      eax, 80070000h
0x1800a38f0  xor     r8d, r8d; int
0x1800a38f3  xor     edx, edx; void *
0x1800a38f5  mov     ecx, eax; int
0x1800a38f7  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x1800a38fd  xor     r9d, r9d; lpName
0x1800a3900  xor     r8d, r8d; bInitialState
0x1800a3903  xor     ecx, ecx; lpEventAttributes
0x1800a3905  lea     edx, [r9+1]; bManualReset
0x1800a3909  call    cs:__imp_CreateEventW
0x1800a390f  mov     [rbx+40h], rax
0x1800a3913  test    rax, rax
0x1800a3916  jnz     short loc_1800A3937
0x1800a3918  call    cs:__imp_GetLastError
0x1800a391e  test    eax, eax
0x1800a3920  jle     short loc_1800A392A
0x1800a3922  movzx   eax, ax
0x1800a3925  or      eax, 80070000h
0x1800a392a  xor     r8d, r8d; int
0x1800a392d  xor     edx, edx; void *
0x1800a392f  mov     ecx, eax; int
0x1800a3931  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x1800a3937  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x1800a3940  lea     r8, ?RegistrarThreadProc@RegistrarHost@@CAKPEAX@Z; lpStartAddress
0x1800a3947  mov     r9, rbx; lpParameter
0x1800a394a  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x1800a3952  xor     edx, edx; dwStackSize
0x1800a3954  xor     ecx, ecx; lpThreadAttributes
0x1800a3956  call    cs:__imp_CreateThread
0x1800a395c  mov     [rbx+30h], rax
0x1800a3960  mov     rcx, rax
0x1800a3963  test    rax, rax
0x1800a3966  jnz     short loc_1800A3987
0x1800a3968  call    cs:__imp_GetLastError
0x1800a396e  test    eax, eax
0x1800a3970  jle     short loc_1800A397A
0x1800a3972  movzx   eax, ax
0x1800a3975  or      eax, 80070000h
0x1800a397a  xor     r8d, r8d; int
0x1800a397d  xor     edx, edx; void *
0x1800a397f  mov     ecx, eax; int
0x1800a3981  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x1800a3987  mov     rax, [rbx+38h]
0x1800a398b  lea     rdx, [rsp+68h+Handles]; lpHandles
0x1800a3990  xor     r8d, r8d; bWaitAll
0x1800a3993  mov     [rsp+68h+var_30], rcx
0x1800a3998  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800a399c  mov     [rsp+68h+Handles], rax
0x1800a39a1  lea     ecx, [r8+2]; nCount
0x1800a39a5  call    cs:__imp_WaitForMultipleObjects
0x1800a39ab  test    eax, eax
0x1800a39ad  jz      short loc_1800A39B5
0x1800a39af  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x1800a39b5  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 4
0x1800a39bc  jz      short loc_1800A39DA
0x1800a39be  lea     rax, [rsp+68h+var_28]
0x1800a39c3  mov     r9d, 1
0x1800a39c9  lea     rdx, CoreUIService_InitializeService
0x1800a39d0  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x1800a39d5  call    McGenEventWrite_EventWriteTransfer
0x1800a39da  mov     rcx, [rbx+38h]; hObject
0x1800a39de  call    cs:__imp_CloseHandle
0x1800a39e4  mov     qword ptr [rbx+38h], 0
0x1800a39ec  mov     rcx, [rsp+68h+var_18]
0x1800a39f1  xor     rcx, rsp; StackCookie
0x1800a39f4  call    __security_check_cookie
0x1800a39f9  add     rsp, 60h
0x1800a39fd  pop     rbx
0x1800a39fe  retn
```
