# CxsWorkerThread(void *)

- ea: `0x18000aa40`
- end: `0x18000ac62`
- name: `?CxsWorkerThread@@YAKPEAX@Z`
- size: `546`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180002b48`
- `0x180002b70`
- `0x18000a02c`
- `0x18000a36c`
- `0x18000aa40`
- `0x18000adf0`
- `0x18000ae98`
- `0x18000ba20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abbc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000aba9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000aba9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000abf3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000abf3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000aa93`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000aa93`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000ab1e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000ab1e`

## pseudocode

```c
__int64 __fastcall CxsWorkerThread(char *Parameter)
{
  SC_HANDLE v2; // rax
  DWORD LastError; // eax
  unsigned int started; // edi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  SC_HANDLE v7; // rax
  CsxManager *v8; // rcx
  DWORD v9; // eax
  DWORD v10; // eax
  void *v11; // rbp

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids);
  }
  v2 = OpenSCManagerW(0, 0, 1u);
  *((_QWORD *)Parameter + 10) = v2;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 21);
    }
    v7 = OpenServiceW(*((SC_HANDLE *)Parameter + 10), L"wlansvc", 4u);
    *((_QWORD *)Parameter + 9) = v7;
    if ( v7 )
    {
      v8 = (CsxManager *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23);
      }
      started = CsxManager::Initialize(v8);
    }
    else
    {
      LastError = GetLastError();
      started = LastError;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v6 = 22;
        goto LABEL_10;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    started = LastError;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v6 = 20;
LABEL_10:
      WPP_SF_D(v5[2], v6, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids, LastError);
    }
  }
  if ( started )
  {
    CxsCloseWlanService((SC_HANDLE *)Parameter);
  }
  else
  {
    started = CxsStartWlanNotification((struct _GIP_WLAN_CLIENT *)Parameter);
    if ( !started )
    {
      do
      {
        v9 = WaitForSingleObjectEx(*((HANDLE *)Parameter + 6), 0xFFFFFFFF, 1);
        started = v9;
      }
      while ( v9 == 192 );
      if ( v9 )
      {
        v10 = GetLastError();
        started = v10;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids, v10);
        }
      }
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
  v11 = (void *)*((_QWORD *)Parameter + 8);
  *(_DWORD *)Parameter |= 2u;
  *((_QWORD *)Parameter + 8) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
  if ( v11 )
    CxspUnregisterWlanNotification(v11);
  CxsCloseWlanService((SC_HANDLE *)Parameter);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids, started);
  }
  return started;
}

```

## disassembly

```asm
0x18000aa40  push    rbx
0x18000aa42  push    rbp
0x18000aa43  push    rsi
0x18000aa44  push    rdi
0x18000aa45  push    r13
0x18000aa47  push    r15
0x18000aa49  sub     rsp, 28h
0x18000aa4d  mov     rsi, rcx
0x18000aa50  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa57  lea     r15, WPP_GLOBAL_Control
0x18000aa5e  lea     r13, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids
0x18000aa65  cmp     rcx, r15
0x18000aa68  jz      short loc_18000AA87
0x18000aa6a  test    byte ptr [rcx+1Ch], 4
0x18000aa6e  jz      short loc_18000AA87
0x18000aa70  cmp     byte ptr [rcx+19h], 5
0x18000aa74  jb      short loc_18000AA87
0x18000aa76  mov     rcx, [rcx+10h]
0x18000aa7a  mov     edx, 25h ; '%'
0x18000aa7f  mov     r8, r13
0x18000aa82  call    WPP_SF_
0x18000aa87  mov     ebx, 1
0x18000aa8c  xor     edx, edx; lpDatabaseName
0x18000aa8e  mov     r8d, ebx; dwDesiredAccess
0x18000aa91  xor     ecx, ecx; lpMachineName
0x18000aa93  call    cs:__imp_OpenSCManagerW
0x18000aa99  mov     [rsi+50h], rax
0x18000aa9d  test    rax, rax
0x18000aaa0  jnz     short loc_18000AAE4
0x18000aaa2  call    cs:__imp_GetLastError
0x18000aaa8  mov     edi, eax
0x18000aaaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aab1  cmp     rcx, r15
0x18000aab4  jz      loc_18000AB86
0x18000aaba  test    byte ptr [rcx+1Ch], 4
0x18000aabe  jz      loc_18000AB86
0x18000aac4  cmp     [rcx+19h], bl
0x18000aac7  jb      loc_18000AB86
0x18000aacd  lea     edx, [rbx+13h]
0x18000aad0  mov     rcx, [rcx+10h]
0x18000aad4  mov     r9d, eax
0x18000aad7  mov     r8, r13
0x18000aada  call    WPP_SF_D
0x18000aadf  jmp     loc_18000AB86
0x18000aae4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaeb  cmp     rcx, r15
0x18000aaee  jz      short loc_18000AB0D
0x18000aaf0  test    byte ptr [rcx+1Ch], 4
0x18000aaf4  jz      short loc_18000AB0D
0x18000aaf6  cmp     byte ptr [rcx+19h], 5
0x18000aafa  jb      short loc_18000AB0D
0x18000aafc  mov     rcx, [rcx+10h]
0x18000ab00  mov     edx, 15h
0x18000ab05  mov     r9, rax
0x18000ab08  call    WPP_SF_q
0x18000ab0d  mov     rcx, [rsi+50h]; hSCManager
0x18000ab11  lea     rdx, aWlansvc; "wlansvc"
0x18000ab18  mov     r8d, 4; dwDesiredAccess
0x18000ab1e  call    cs:__imp_OpenServiceW
0x18000ab24  mov     [rsi+48h], rax
0x18000ab28  test    rax, rax
0x18000ab2b  jnz     short loc_18000AB56
0x18000ab2d  call    cs:__imp_GetLastError
0x18000ab33  mov     edi, eax
0x18000ab35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab3c  cmp     rcx, r15
0x18000ab3f  jz      short loc_18000AB86
0x18000ab41  test    byte ptr [rcx+1Ch], 4
0x18000ab45  jz      short loc_18000AB86
0x18000ab47  cmp     [rcx+19h], bl
0x18000ab4a  jb      short loc_18000AB86
0x18000ab4c  mov     edx, 16h
0x18000ab51  jmp     loc_18000AAD0
0x18000ab56  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab5d  cmp     rcx, r15
0x18000ab60  jz      short loc_18000AB7F
0x18000ab62  test    byte ptr [rcx+1Ch], 4
0x18000ab66  jz      short loc_18000AB7F
0x18000ab68  cmp     byte ptr [rcx+19h], 5
0x18000ab6c  jb      short loc_18000AB7F
0x18000ab6e  mov     rcx, [rcx+10h]
0x18000ab72  mov     edx, 17h
0x18000ab77  mov     r9, rax
0x18000ab7a  call    WPP_SF_q
0x18000ab7f  call    ?Initialize@CsxManager@@QEAAKXZ; CsxManager::Initialize(void)
0x18000ab84  mov     edi, eax
0x18000ab86  mov     rcx, rsi; struct _GIP_WLAN_CLIENT *
0x18000ab89  test    edi, edi
0x18000ab8b  jz      short loc_18000AB94
0x18000ab8d  call    ?CxsCloseWlanService@@YAXPEAU_GIP_WLAN_CLIENT@@@Z; CxsCloseWlanService(_GIP_WLAN_CLIENT *)
0x18000ab92  jmp     short loc_18000ABEF
0x18000ab94  call    ?CxsStartWlanNotification@@YAKPEAU_GIP_WLAN_CLIENT@@@Z; CxsStartWlanNotification(_GIP_WLAN_CLIENT *)
0x18000ab99  mov     edi, eax
0x18000ab9b  test    eax, eax
0x18000ab9d  jnz     short loc_18000ABEF
0x18000ab9f  mov     rcx, [rsi+30h]; hHandle
0x18000aba3  mov     r8d, ebx; bAlertable
0x18000aba6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000aba9  call    cs:__imp_WaitForSingleObjectEx
0x18000abaf  mov     edi, eax
0x18000abb1  cmp     eax, 0C0h
0x18000abb6  jz      short loc_18000AB9F
0x18000abb8  test    eax, eax
0x18000abba  jz      short loc_18000ABEF
0x18000abbc  call    cs:__imp_GetLastError
0x18000abc2  mov     edi, eax
0x18000abc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abcb  cmp     rcx, r15
0x18000abce  jz      short loc_18000ABEF
0x18000abd0  test    byte ptr [rcx+1Ch], 4
0x18000abd4  jz      short loc_18000ABEF
0x18000abd6  cmp     [rcx+19h], bl
0x18000abd9  jb      short loc_18000ABEF
0x18000abdb  mov     rcx, [rcx+10h]
0x18000abdf  mov     edx, 26h ; '&'
0x18000abe4  mov     r9d, eax
0x18000abe7  mov     r8, r13
0x18000abea  call    WPP_SF_D
0x18000abef  lea     rcx, [rsi+8]; lpCriticalSection
0x18000abf3  call    cs:__imp_EnterCriticalSection
0x18000abf9  mov     rbp, [rsi+40h]
0x18000abfd  lea     rcx, [rsi+8]; lpCriticalSection
0x18000ac01  or      dword ptr [rsi], 2
0x18000ac04  mov     qword ptr [rsi+40h], 0
0x18000ac0c  call    cs:__imp_LeaveCriticalSection
0x18000ac12  test    rbp, rbp
0x18000ac15  jz      short loc_18000AC1F
0x18000ac17  mov     rcx, rbp; hClientHandle
0x18000ac1a  call    ?CxspUnregisterWlanNotification@@YAXPEAX@Z; CxspUnregisterWlanNotification(void *)
0x18000ac1f  mov     rcx, rsi; struct _GIP_WLAN_CLIENT *
0x18000ac22  call    ?CxsCloseWlanService@@YAXPEAU_GIP_WLAN_CLIENT@@@Z; CxsCloseWlanService(_GIP_WLAN_CLIENT *)
0x18000ac27  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac2e  cmp     rcx, r15
0x18000ac31  jz      short loc_18000AC53
0x18000ac33  test    byte ptr [rcx+1Ch], 4
0x18000ac37  jz      short loc_18000AC53
0x18000ac39  cmp     byte ptr [rcx+19h], 5
0x18000ac3d  jb      short loc_18000AC53
0x18000ac3f  mov     rcx, [rcx+10h]
0x18000ac43  mov     edx, 27h ; '''
0x18000ac48  mov     r9d, edi
0x18000ac4b  mov     r8, r13
0x18000ac4e  call    WPP_SF_D
0x18000ac53  mov     eax, edi
0x18000ac55  add     rsp, 28h
0x18000ac59  pop     r15
0x18000ac5b  pop     r13
0x18000ac5d  pop     rdi
0x18000ac5e  pop     rsi
0x18000ac5f  pop     rbp
0x18000ac60  pop     rbx
0x18000ac61  retn
```
