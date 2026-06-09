# CommonUtil::HrStopService(wchar_t const *,ulong)

- ea: `0x140016538`
- end: `0x1400166d3`
- name: `?HrStopService@CommonUtil@@YAJPEB_WK@Z`
- size: `411`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *this, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x14008ab48`

## callees

- `0x140015e60`
- `0x140016064`
- `0x1400160cc`
- `0x140016538`
- `0x1400166d4`
- `0x14007d210`
- `0x140085d94`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x140016579`
- `ADVAPI32!CloseServiceHandle` at `0x1400165bd`
- `ADVAPI32!CloseServiceHandle` at `0x1400165cb`
- `ADVAPI32!CloseServiceHandle` at `0x14001661d`
- `ADVAPI32!CloseServiceHandle` at `0x14001662b`
- `ADVAPI32!CloseServiceHandle` at `0x1400166b0`
- `ADVAPI32!CloseServiceHandle` at `0x1400166be`
- `ADVAPI32!CloseServiceHandle` at `0x140016579`
- `ADVAPI32!CloseServiceHandle` at `0x1400165bd`
- `ADVAPI32!CloseServiceHandle` at `0x1400165cb`
- `ADVAPI32!CloseServiceHandle` at `0x14001661d`
- `ADVAPI32!CloseServiceHandle` at `0x14001662b`
- `ADVAPI32!CloseServiceHandle` at `0x1400166b0`
- `ADVAPI32!CloseServiceHandle` at `0x1400166be`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrStopService(struct SC_HANDLE__ *this, const wchar_t *a2)
{
  unsigned int v2; // esi
  int v4; // ebx
  SC_HANDLE v6; // rbx
  int v7; // eax
  struct _SERVICE_STATUS *v8; // r9
  unsigned int v9; // edi
  SC_HANDLE v10; // rdi
  int v11; // esi
  const wchar_t *v12; // [rsp+20h] [rbp-38h]
  unsigned int v13; // [rsp+20h] [rbp-38h]
  unsigned int v14; // [rsp+28h] [rbp-30h]
  SC_HANDLE hService; // [rsp+30h] [rbp-28h] BYREF
  SC_HANDLE hSCObject[4]; // [rsp+38h] [rbp-20h] BYREF

  hSCObject[0] = 0;
  v2 = (unsigned int)a2;
  v4 = CommonUtil::HrOpenSCManager((CommonUtil *)hSCObject, (struct SC_HANDLE__ **)1, 0, 0, v12);
  if ( v4 >= 0 )
  {
    v6 = hSCObject[0];
    hService = 0;
    v7 = CommonUtil::HrOpenService(
           (CommonUtil *)&hService,
           (struct SC_HANDLE__ **)hSCObject[0],
           this,
           (const wchar_t *)0x24,
           v13);
    v9 = v7;
    if ( v7 == -2147023836 )
    {
      if ( hService )
        CloseServiceHandle(hService);
      if ( v6 )
        CloseServiceHandle(v6);
      return 1;
    }
    else if ( v7 >= 0 )
    {
      v10 = hService;
      CommonUtil::HrControlService(hService, (struct SC_HANDLE__ *)1, 0, v8);
      v11 = CommonUtil::HrUtilWaitForServiceStatus(v10, (struct SC_HANDLE__ *)v2, 1u, 3u, 0, v14);
      if ( v11 < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          35,
          (unsigned int)WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids,
          (_DWORD)this,
          v11);
      }
      if ( v10 )
        CloseServiceHandle(v10);
      if ( v6 )
        CloseServiceHandle(v6);
      return (unsigned int)v11;
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          34,
          WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids,
          (unsigned int)v7);
      if ( hService )
        CloseServiceHandle(hService);
      if ( v6 )
        CloseServiceHandle(v6);
      return v9;
    }
  }
  else
  {
    if ( hSCObject[0] )
      CloseServiceHandle(hSCObject[0]);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x140016538  mov     [rsp+arg_10], rbx
0x14001653d  push    rbp
0x14001653e  push    rsi
0x14001653f  push    rdi
0x140016540  sub     rsp, 40h
0x140016544  xor     r9d, r9d; wchar_t *
0x140016547  mov     [rsp+58h+hSCObject], 0
0x140016550  mov     esi, edx
0x140016552  mov     rbp, rcx
0x140016555  xor     r8d, r8d; unsigned int
0x140016558  lea     rcx, [rsp+58h+hSCObject]; this
0x14001655d  lea     edx, [r9+1]; struct SC_HANDLE__ **
0x140016561  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEB_W1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,wchar_t const *,wchar_t const *)
0x140016566  mov     ebx, eax
0x140016568  shr     eax, 1Fh
0x14001656b  test    al, al
0x14001656d  jz      short loc_140016586
0x14001656f  mov     rcx, [rsp+58h+hSCObject]; hSCObject
0x140016574  test    rcx, rcx
0x140016577  jz      short loc_14001657F
0x140016579  call    cs:__imp_CloseServiceHandle
0x14001657f  mov     eax, ebx
0x140016581  jmp     loc_1400166C6
0x140016586  mov     rbx, [rsp+58h+hSCObject]
0x14001658b  lea     rcx, [rsp+58h+hService]; this
0x140016590  mov     rdx, rbx; struct SC_HANDLE__ **
0x140016593  mov     [rsp+58h+hService], 0
0x14001659c  mov     r9d, 24h ; '$'; wchar_t *
0x1400165a2  mov     r8, rbp; struct SC_HANDLE__ *
0x1400165a5  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEB_WK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,wchar_t const *,ulong)
0x1400165aa  mov     edi, eax
0x1400165ac  cmp     eax, 80070424h
0x1400165b1  jnz     short loc_1400165DB
0x1400165b3  mov     rcx, [rsp+58h+hService]; hSCObject
0x1400165b8  test    rcx, rcx
0x1400165bb  jz      short loc_1400165C3
0x1400165bd  call    cs:__imp_CloseServiceHandle
0x1400165c3  test    rbx, rbx
0x1400165c6  jz      short loc_1400165D1
0x1400165c8  mov     rcx, rbx; hSCObject
0x1400165cb  call    cs:__imp_CloseServiceHandle
0x1400165d1  mov     eax, 1
0x1400165d6  jmp     loc_1400166C6
0x1400165db  shr     eax, 1Fh
0x1400165de  test    al, al
0x1400165e0  jz      short loc_140016638
0x1400165e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400165e9  lea     rax, WPP_GLOBAL_Control
0x1400165f0  cmp     rcx, rax
0x1400165f3  jz      short loc_140016613
0x1400165f5  test    byte ptr [rcx+1Ch], 1
0x1400165f9  jz      short loc_140016613
0x1400165fb  mov     rcx, [rcx+10h]
0x1400165ff  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140016606  mov     edx, 22h ; '"'
0x14001660b  mov     r9d, edi
0x14001660e  call    WPP_SF_d
0x140016613  mov     rcx, [rsp+58h+hService]; hSCObject
0x140016618  test    rcx, rcx
0x14001661b  jz      short loc_140016623
0x14001661d  call    cs:__imp_CloseServiceHandle
0x140016623  test    rbx, rbx
0x140016626  jz      short loc_140016631
0x140016628  mov     rcx, rbx; hSCObject
0x14001662b  call    cs:__imp_CloseServiceHandle
0x140016631  mov     eax, edi
0x140016633  jmp     loc_1400166C6
0x140016638  mov     rdi, [rsp+58h+hService]
0x14001663d  xor     r8d, r8d; lpServiceStatus
0x140016640  mov     rcx, rdi; hService
0x140016643  lea     edx, [r8+1]; this
0x140016647  call    ?HrControlService@CommonUtil@@YAJPEAUSC_HANDLE__@@KPEAU_SERVICE_STATUS@@@Z; CommonUtil::HrControlService(SC_HANDLE__ *,ulong,_SERVICE_STATUS *)
0x14001664c  mov     r9d, 3; unsigned int
0x140016652  mov     dword ptr [rsp+58h+var_38], 0; unsigned int
0x14001665a  mov     edx, esi; struct SC_HANDLE__ *
0x14001665c  mov     rcx, rdi; hService
0x14001665f  lea     r8d, [r9-2]; unsigned int
0x140016663  call    ?HrUtilWaitForServiceStatus@CommonUtil@@YAJPEAUSC_HANDLE__@@KKKK@Z; CommonUtil::HrUtilWaitForServiceStatus(SC_HANDLE__ *,ulong,ulong,ulong,ulong)
0x140016668  mov     ecx, eax
0x14001666a  mov     esi, eax
0x14001666c  shr     ecx, 1Fh
0x14001666f  test    cl, cl
0x140016671  jz      short loc_1400166A8
0x140016673  mov     rcx, cs:WPP_GLOBAL_Control
0x14001667a  lea     rax, WPP_GLOBAL_Control
0x140016681  cmp     rcx, rax
0x140016684  jz      short loc_1400166A8
0x140016686  test    byte ptr [rcx+1Ch], 1
0x14001668a  jz      short loc_1400166A8
0x14001668c  mov     rcx, [rcx+10h]
0x140016690  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140016697  mov     edx, 23h ; '#'
0x14001669c  mov     dword ptr [rsp+58h+var_38], esi
0x1400166a0  mov     r9, rbp
0x1400166a3  call    WPP_SF_Sd
0x1400166a8  test    rdi, rdi
0x1400166ab  jz      short loc_1400166B6
0x1400166ad  mov     rcx, rdi; hSCObject
0x1400166b0  call    cs:__imp_CloseServiceHandle
0x1400166b6  test    rbx, rbx
0x1400166b9  jz      short loc_1400166C4
0x1400166bb  mov     rcx, rbx; hSCObject
0x1400166be  call    cs:__imp_CloseServiceHandle
0x1400166c4  mov     eax, esi
0x1400166c6  mov     rbx, [rsp+58h+arg_10]
0x1400166cb  add     rsp, 40h
0x1400166cf  pop     rdi
0x1400166d0  pop     rsi
0x1400166d1  pop     rbp
0x1400166d2  retn
```
