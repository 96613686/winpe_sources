# CUserVaultMgr::InitializeOnLogon(void *)

- ea: `0x180030f60`
- end: `0x180031098`
- name: `?InitializeOnLogon@CUserVaultMgr@@QEAAKPEAX@Z`
- size: `312`
- prototype: `__int64 __fastcall(CUserVaultMgr *this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ba80`

## callees

- `0x180030f60`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180031006`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180031006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003105a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003105a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030fde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030fde`
- `ntdll!RtlReleaseResource` at `0x180031015`
- `ntdll!RtlReleaseResource` at `0x180031015`
- `ntdll!RtlAcquireResourceExclusive` at `0x180030f7e`
- `ntdll!RtlAcquireResourceExclusive` at `0x180030f7e`
- `ntdll!RtlNtStatusToDosError` at `0x18003102f`
- `ntdll!RtlNtStatusToDosError` at `0x18003102f`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180030fc0`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180030fc0`

## pseudocode

```c
__int64 __fastcall CUserVaultMgr::InitializeOnLogon(CUserVaultMgr *this, void *a2)
{
  struct _RTL_RESOURCE *v2; // rdi
  NTSTATUS v5; // eax
  HANDLE *phNewToken; // rbx
  DWORD v7; // ebx
  ULONG v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  DWORD LastError; // eax

  v2 = (struct _RTL_RESOURCE *)((char *)this + 72);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 72), 1u);
  if ( *((_QWORD *)this + 22)
    || (v5 = RtlSubscribeWnfStateChangeNotification(
               (char *)this + 176,
               WNF_TKBR_CHANGE_APP,
               0,
               _scrt_stub_for_is_c_termination_complete,
               this,
               0,
               0,
               1),
        v5 >= 0) )
  {
    if ( !a2 )
      goto LABEL_7;
    phNewToken = (HANDLE *)((char *)this + 184);
    if ( *phNewToken )
    {
      CloseHandle(*phNewToken);
      *phNewToken = 0;
    }
    if ( DuplicateTokenEx(a2, 0, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
    {
LABEL_7:
      v7 = 0;
      goto LABEL_8;
    }
    LastError = GetLastError();
    v7 = LastError;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = 50;
      v12 = LastError;
      goto LABEL_15;
    }
  }
  else
  {
    v9 = RtlNtStatusToDosError(v5);
    v7 = v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = 49;
      v12 = v9;
LABEL_15:
      WPP_SF_d(v10[2], v11, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, v12);
    }
  }
LABEL_8:
  RtlReleaseResource(v2);
  return v7;
}

```

## disassembly

```asm
0x180030f60  mov     [rsp+arg_0], rbx
0x180030f65  mov     [rsp+arg_8], rsi
0x180030f6a  push    rdi
0x180030f6b  sub     rsp, 40h
0x180030f6f  lea     rdi, [rcx+48h]
0x180030f73  mov     rsi, rdx
0x180030f76  mov     rbx, rcx
0x180030f79  mov     dl, 1; Wait
0x180030f7b  mov     rcx, rdi; Resource
0x180030f7e  call    cs:__imp_RtlAcquireResourceExclusive
0x180030f84  lea     rcx, [rbx+0B0h]
0x180030f8b  cmp     qword ptr [rcx], 0
0x180030f8f  jnz     short loc_180030FCA
0x180030f91  mov     rdx, cs:WNF_TKBR_CHANGE_APP
0x180030f98  lea     r9, __scrt_stub_for_is_c_termination_complete
0x180030f9f  mov     [rsp+48h+var_10], 1
0x180030fa7  xor     r8d, r8d
0x180030faa  mov     [rsp+48h+var_18], 0
0x180030fb2  mov     [rsp+48h+phNewToken], 0
0x180030fbb  mov     qword ptr [rsp+48h+TokenType], rbx
0x180030fc0  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180030fc6  test    eax, eax
0x180030fc8  js      short loc_18003102D
0x180030fca  test    rsi, rsi
0x180030fcd  jz      short loc_180031010
0x180030fcf  add     rbx, 0B8h
0x180030fd6  mov     rcx, [rbx]; hObject
0x180030fd9  test    rcx, rcx
0x180030fdc  jz      short loc_180030FEB
0x180030fde  call    cs:__imp_CloseHandle
0x180030fe4  mov     qword ptr [rbx], 0
0x180030feb  mov     [rsp+48h+phNewToken], rbx; phNewToken
0x180030ff0  mov     r9d, 2; ImpersonationLevel
0x180030ff6  xor     r8d, r8d; lpTokenAttributes
0x180030ff9  mov     [rsp+48h+TokenType], 2; TokenType
0x180031001  xor     edx, edx; dwDesiredAccess
0x180031003  mov     rcx, rsi; hExistingToken
0x180031006  call    cs:__imp_DuplicateTokenEx
0x18003100c  test    eax, eax
0x18003100e  jz      short loc_18003105A
0x180031010  xor     ebx, ebx
0x180031012  mov     rcx, rdi; Resource
0x180031015  call    cs:__imp_RtlReleaseResource
0x18003101b  mov     rsi, [rsp+48h+arg_8]
0x180031020  mov     eax, ebx
0x180031022  mov     rbx, [rsp+48h+arg_0]
0x180031027  add     rsp, 40h
0x18003102b  pop     rdi
0x18003102c  retn
0x18003102d  mov     ecx, eax; Status
0x18003102f  call    cs:__imp_RtlNtStatusToDosError
0x180031035  mov     ebx, eax
0x180031037  mov     rcx, cs:WPP_GLOBAL_Control
0x18003103e  lea     rdx, WPP_GLOBAL_Control
0x180031045  cmp     rcx, rdx
0x180031048  jz      short loc_180031012
0x18003104a  test    byte ptr [rcx+1Ch], 2
0x18003104e  jz      short loc_180031012
0x180031050  mov     edx, 31h ; '1'
0x180031055  mov     r9d, eax
0x180031058  jmp     short loc_180031083
0x18003105a  call    cs:__imp_GetLastError
0x180031060  mov     ebx, eax
0x180031062  mov     rcx, cs:WPP_GLOBAL_Control
0x180031069  lea     rdx, WPP_GLOBAL_Control
0x180031070  cmp     rcx, rdx
0x180031073  jz      short loc_180031012
0x180031075  test    byte ptr [rcx+1Ch], 2
0x180031079  jz      short loc_180031012
0x18003107b  mov     edx, 32h ; '2'
0x180031080  mov     r9d, eax
0x180031083  mov     rcx, [rcx+10h]
0x180031087  lea     r8, WPP_f1575cf6446936089985711df8c7b212_Traceguids
0x18003108e  call    WPP_SF_d
0x180031093  jmp     loc_180031012
```
