# CAxisServModule::Initialize(void)

- ea: `0x18000c224`
- end: `0x18000c3d0`
- name: `?Initialize@CAxisServModule@@QEAAJXZ`
- size: `428`
- prototype: `__int64 __fastcall(CAxisServModule *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000f170`

## callees

- `0x180003a88`
- `0x180003afc`
- `0x180004364`
- `0x18000725c`
- `0x18000bf6c`
- `0x18000c224`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000c35a`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000c35a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c392`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c2f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c32c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c2f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c32c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000c258`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000c258`
- `USERENV!RegisterGPNotification` at `0x18000c388`
- `USERENV!RegisterGPNotification` at `0x18000c388`

## string_xrefs

- `0x18000c2c9`: `Error Reading Policy 0x%x`
- `0x18000c2e0`: `Failed to update the policy using GP Policy 0x%x`
- `0x18000c36f`: `Failed to start policy notification thread 0x%x`

## pseudocode

```c
__int64 __fastcall CAxisServModule::Initialize(CAxisServModule *this)
{
  char *v1; // rbx
  int Policy; // eax
  unsigned int v4; // ebx
  unsigned __int16 *v5; // r9
  HANDLE EventW; // rax
  signed int v7; // eax
  HANDLE v8; // rax
  __int64 v9; // rax
  signed int LastError; // eax
  int v12; // [rsp+20h] [rbp-18h]
  __int64 v13; // [rsp+20h] [rbp-18h]

  v1 = (char *)this + 1256;
  if ( !*((_DWORD *)this + 316)
    && !EventRegister(
          &AXISSERVICE_PUBLISHER,
          AxISEvents::s_ControlCallback,
          (char *)this + 1256,
          (PREGHANDLE)this + 161) )
  {
    *((_DWORD *)v1 + 2) = 1;
  }
  Policy = CAxisServHelper::Initialize((CAxisServModule *)((char *)this + 120));
  v4 = Policy;
  if ( Policy < 0 )
  {
    v5 = L"Failed to Init Helper object 0x%x";
LABEL_6:
    v12 = Policy;
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, v5, v12);
    return v4;
  }
  Policy = CPolicyCheck::Initialize((CAxisServModule *)((char *)this + 1296));
  v4 = Policy;
  if ( Policy < 0 )
  {
    v5 = L"Error Initializing Policy 0x%x";
    goto LABEL_6;
  }
  Policy = CPolicyCheck::ReadPolicy((CAxisServModule *)((char *)this + 1296));
  v4 = Policy;
  if ( Policy < 0 )
  {
    v5 = L"Error Reading Policy 0x%x";
    goto LABEL_6;
  }
  Policy = CPolicyCheck::UpdatePolicyFromGP((HKEY *)this + 162);
  v4 = Policy;
  if ( Policy < 0 )
  {
    v5 = L"Failed to update the policy using GP Policy 0x%x";
    goto LABEL_6;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 10) = EventW;
  if ( EventW && (v8 = CreateEventW(0, 0, 0, 0), (*((_QWORD *)this + 11) = v8) != 0) )
  {
    v9 = _o__beginthreadex(0, 0, CAxisServModule::_HandleNotifications, this, 0, (char *)this + 112);
    *((_QWORD *)this + 13) = v9;
    if ( v9 == -1 )
    {
      v4 = -2147467259;
      LODWORD(v13) = -2147467259;
      AxISEvents::DebugMsg(
        (AxISEvents *)&qword_180021AD8,
        8u,
        2u,
        L"Failed to start policy notification thread 0x%x",
        v13);
    }
    else if ( RegisterGPNotification(*((HANDLE *)this + 11), 1) )
    {
      *((_DWORD *)this + 24) = 1;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v13) = v4;
      AxISEvents::DebugMsg(
        (AxISEvents *)&qword_180021AD8,
        8u,
        2u,
        L"Failed to register for Group Policy notification 0x%x",
        v13);
    }
  }
  else
  {
    v7 = GetLastError();
    v4 = v7;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x18000c224  mov     [rsp+arg_0], rbx
0x18000c229  mov     [rsp+arg_8], rsi
0x18000c22e  push    rdi
0x18000c22f  sub     rsp, 30h
0x18000c233  lea     rbx, [rcx+4E8h]
0x18000c23a  mov     rdi, rcx
0x18000c23d  cmp     dword ptr [rbx+8], 0
0x18000c241  jnz     short loc_18000C269
0x18000c243  lea     r9, [rbx+20h]; RegHandle
0x18000c247  mov     r8, rbx; CallbackContext
0x18000c24a  lea     rdx, ?s_ControlCallback@AxISEvents@@SAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; EnableCallback
0x18000c251  lea     rcx, AXISSERVICE_PUBLISHER; ProviderId
0x18000c258  call    cs:__imp_EventRegister
0x18000c25e  test    eax, eax
0x18000c260  jnz     short loc_18000C269
0x18000c262  mov     dword ptr [rbx+8], 1
0x18000c269  lea     rcx, [rdi+78h]; this
0x18000c26d  call    ?Initialize@CAxisServHelper@@QEAAJXZ; CAxisServHelper::Initialize(void)
0x18000c272  mov     ebx, eax
0x18000c274  test    eax, eax
0x18000c276  jns     short loc_18000C29D
0x18000c278  lea     r9, aFailedToInitHe; "Failed to Init Helper object 0x%x"
0x18000c27f  mov     dword ptr [rsp+38h+var_18], eax
0x18000c283  mov     edx, 8; unsigned int
0x18000c288  lea     rcx, qword_180021AD8; this
0x18000c28f  lea     r8d, [rdx-6]; unsigned __int8
0x18000c293  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000c298  jmp     loc_18000C3BE
0x18000c29d  lea     rsi, [rdi+510h]
0x18000c2a4  mov     rcx, rsi; this
0x18000c2a7  call    ?Initialize@CPolicyCheck@@QEAAJXZ; CPolicyCheck::Initialize(void)
0x18000c2ac  mov     ebx, eax
0x18000c2ae  test    eax, eax
0x18000c2b0  jns     short loc_18000C2BB
0x18000c2b2  lea     r9, aErrorInitializ; "Error Initializing Policy 0x%x"
0x18000c2b9  jmp     short loc_18000C27F
0x18000c2bb  mov     rcx, rsi; this
0x18000c2be  call    ?ReadPolicy@CPolicyCheck@@QEAAJXZ; CPolicyCheck::ReadPolicy(void)
0x18000c2c3  mov     ebx, eax
0x18000c2c5  test    eax, eax
0x18000c2c7  jns     short loc_18000C2D2
0x18000c2c9  lea     r9, aErrorReadingPo; "Error Reading Policy 0x%x"
0x18000c2d0  jmp     short loc_18000C27F
0x18000c2d2  mov     rcx, rsi; this
0x18000c2d5  call    ?UpdatePolicyFromGP@CPolicyCheck@@QEAAJXZ; CPolicyCheck::UpdatePolicyFromGP(void)
0x18000c2da  mov     ebx, eax
0x18000c2dc  test    eax, eax
0x18000c2de  jns     short loc_18000C2E9
0x18000c2e0  lea     r9, aFailedToUpdate; "Failed to update the policy using GP Po"...
0x18000c2e7  jmp     short loc_18000C27F
0x18000c2e9  xor     r9d, r9d; lpName
0x18000c2ec  xor     r8d, r8d; bInitialState
0x18000c2ef  xor     ecx, ecx; lpEventAttributes
0x18000c2f1  lea     edx, [r9+1]; bManualReset
0x18000c2f5  call    cs:__imp_CreateEventW
0x18000c2fb  mov     [rdi+50h], rax
0x18000c2ff  test    rax, rax
0x18000c302  jnz     short loc_18000C322
0x18000c304  call    cs:__imp_GetLastError
0x18000c30a  mov     ebx, eax
0x18000c30c  test    eax, eax
0x18000c30e  jle     loc_18000C3BE
0x18000c314  movzx   ebx, ax
0x18000c317  or      ebx, 80070000h
0x18000c31d  jmp     loc_18000C3BE
0x18000c322  xor     r9d, r9d; lpName
0x18000c325  xor     r8d, r8d; bInitialState
0x18000c328  xor     edx, edx; bManualReset
0x18000c32a  xor     ecx, ecx; lpEventAttributes
0x18000c32c  call    cs:__imp_CreateEventW
0x18000c332  mov     [rdi+58h], rax
0x18000c336  test    rax, rax
0x18000c339  jz      short loc_18000C304
0x18000c33b  lea     rax, [rdi+70h]
0x18000c33f  mov     r9, rdi
0x18000c342  mov     [rsp+38h+var_10], rax
0x18000c347  lea     r8, ?_HandleNotifications@CAxisServModule@@SAIPEAX@Z; CAxisServModule::_HandleNotifications(void *)
0x18000c34e  xor     edx, edx
0x18000c350  mov     dword ptr [rsp+38h+var_18], 0
0x18000c358  xor     ecx, ecx
0x18000c35a  call    cs:__imp__o__beginthreadex
0x18000c360  mov     [rdi+68h], rax
0x18000c364  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c368  jnz     short loc_18000C37F
0x18000c36a  mov     ebx, 80004005h
0x18000c36f  lea     r9, aFailedToStartP; "Failed to start policy notification thr"...
0x18000c376  mov     dword ptr [rsp+38h+var_18], ebx
0x18000c37a  jmp     loc_18000C283
0x18000c37f  mov     rcx, [rdi+58h]; hEvent
0x18000c383  mov     edx, 1; bMachine
0x18000c388  call    cs:__imp_RegisterGPNotification
0x18000c38e  test    eax, eax
0x18000c390  jnz     short loc_18000C3B7
0x18000c392  call    cs:__imp_GetLastError
0x18000c398  mov     ebx, eax
0x18000c39a  test    eax, eax
0x18000c39c  jle     short loc_18000C3A7
0x18000c39e  movzx   ebx, ax
0x18000c3a1  or      ebx, 80070000h
0x18000c3a7  mov     dword ptr [rsp+38h+var_18], ebx
0x18000c3ab  lea     r9, aFailedToRegist; "Failed to register for Group Policy not"...
0x18000c3b2  jmp     loc_18000C283
0x18000c3b7  mov     dword ptr [rdi+60h], 1
0x18000c3be  mov     rsi, [rsp+38h+arg_8]
0x18000c3c3  mov     eax, ebx
0x18000c3c5  mov     rbx, [rsp+38h+arg_0]
0x18000c3ca  add     rsp, 30h
0x18000c3ce  pop     rdi
0x18000c3cf  retn
```
