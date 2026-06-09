# ShieldProvider::FirewallManager::StartFwService(void)

- ea: `0x18004c0c0`
- end: `0x18004c2b4`
- name: `?StartFwService@FirewallManager@ShieldProvider@@AEAAJXZ`
- size: `500`
- prototype: `__int64 __fastcall(ShieldProvider::FirewallManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180048668`

## callees

- `0x18000d7fc`
- `0x18004c0c0`
- `0x1800e1944`
- `0x1800e1a1c`
- `0x1800e1a88`
- `0x1800e1bb4`
- `0x1800e1c74`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c132`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c1a8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c1b6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c28a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c298`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c132`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c1a8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c1b6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c28a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004c298`

## pseudocode

```c
__int64 __fastcall ShieldProvider::FirewallManager::StartFwService(
        ShieldProvider::FirewallManager *this,
        struct SC_HANDLE__ **a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  SC_HANDLE v8; // rbx
  int v9; // eax
  struct SC_HANDLE__ *v10; // rdx
  unsigned __int64 v11; // r8
  const unsigned __int16 *const *v12; // r9
  unsigned int v13; // edi
  SC_HANDLE v14; // rdi
  __int64 v15; // r15
  struct SC_HANDLE__ *v16; // rdx
  int started; // ebp
  unsigned int v18; // r8d
  unsigned int v19; // r9d
  int v20; // eax
  struct SC_HANDLE__ *v21; // rdx
  unsigned int v22; // r8d
  unsigned int v23; // r9d
  PVOID *v24; // rcx
  __int64 v25; // rdx
  const unsigned __int16 *v26; // [rsp+20h] [rbp-68h]
  unsigned int v27; // [rsp+20h] [rbp-68h]
  unsigned int v28; // [rsp+20h] [rbp-68h]
  void *v29; // [rsp+20h] [rbp-68h]
  unsigned __int16 *v30; // [rsp+28h] [rbp-60h]
  const struct CommonUtil::IWaitForServiceCancellation *v31; // [rsp+30h] [rbp-58h]
  const unsigned __int16 *v32; // [rsp+30h] [rbp-58h]
  const unsigned __int16 *v33; // [rsp+38h] [rbp-50h]
  const unsigned __int16 *v34; // [rsp+40h] [rbp-48h]
  const unsigned __int16 *v35; // [rsp+48h] [rbp-40h]
  const unsigned __int16 *v36; // [rsp+50h] [rbp-38h]
  unsigned int *v37; // [rsp+58h] [rbp-30h]
  SC_HANDLE hSCObject; // [rsp+98h] [rbp+10h] BYREF
  SC_HANDLE hService; // [rsp+A0h] [rbp+18h] BYREF

  hSCObject = 0;
  hService = 0;
  v5 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, a2, a3, a4, v26);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids,
        (unsigned int)v5);
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return v6;
  }
  v8 = hSCObject;
  v9 = CommonUtil::HrOpenService(
         (CommonUtil *)&hService,
         (struct SC_HANDLE__ **)hSCObject,
         (struct SC_HANDLE__ *)&stru_1800F8688,
         (const unsigned __int16 *)0x16,
         v27);
  v13 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids,
        (unsigned int)v9);
    if ( hService )
      CloseServiceHandle(hService);
    if ( v8 )
      CloseServiceHandle(v8);
    return v13;
  }
  v14 = hService;
  v15 = *((_QWORD *)this + 17);
  started = CommonUtil::HrStartService((CommonUtil *)hService, v10, v11, v12);
  if ( started < 0 )
    goto LABEL_22;
  v20 = CommonUtil::UtilWaitForServiceStatus(v14, v16, v18, v19, v28, v15, v31);
  started = v20;
  if ( v20 >= 0 )
  {
    started = CommonUtil::HrChangeServiceConfig(
                (CommonUtil *)v14,
                v21,
                v22,
                v23,
                v29,
                v30,
                v32,
                v33,
                v34,
                v35,
                v36,
                v37);
    if ( started >= 0 )
    {
      *((_DWORD *)this + 36) = 0;
      goto LABEL_32;
    }
    v24 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_32;
    v25 = 69;
    goto LABEL_26;
  }
  v24 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_23;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_16ffd3dfa2bc3d570eea8a4a30209ffe_Traceguids,
      (unsigned int)v20);
LABEL_22:
    v24 = (PVOID *)WPP_GLOBAL_Control;
LABEL_23:
    if ( v24 == &WPP_GLOBAL_Control || (*((_BYTE *)v24 + 28) & 1) == 0 )
      goto LABEL_32;
    v25 = 68;
LABEL_26:
    WPP_SF_d(v24[2], v25, &WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids, (unsigned int)started);
  }
LABEL_32:
  if ( v14 )
    CloseServiceHandle(v14);
  if ( v8 )
    CloseServiceHandle(v8);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18004c0c0  mov     rax, rsp
0x18004c0c3  mov     [rax+8], rbx
0x18004c0c7  push    rbp
0x18004c0c8  push    rsi
0x18004c0c9  push    rdi
0x18004c0ca  push    r14
0x18004c0cc  push    r15
0x18004c0ce  sub     rsp, 60h
0x18004c0d2  mov     r14, rcx
0x18004c0d5  mov     qword ptr [rax+10h], 0
0x18004c0dd  lea     rcx, [rax+10h]; this
0x18004c0e1  mov     qword ptr [rax+18h], 0
0x18004c0e9  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEBG1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,ushort const *,ushort const *)
0x18004c0ee  mov     ebx, eax
0x18004c0f0  test    eax, eax
0x18004c0f2  jns     short loc_18004C13F
0x18004c0f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c0fb  lea     rsi, WPP_GLOBAL_Control
0x18004c102  cmp     rcx, rsi
0x18004c105  jz      short loc_18004C125
0x18004c107  test    byte ptr [rcx+1Ch], 1
0x18004c10b  jz      short loc_18004C125
0x18004c10d  mov     rcx, [rcx+10h]
0x18004c111  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x18004c118  mov     edx, 42h ; 'B'
0x18004c11d  mov     r9d, eax
0x18004c120  call    WPP_SF_d
0x18004c125  mov     rcx, [rsp+88h+hSCObject]; hSCObject
0x18004c12d  test    rcx, rcx
0x18004c130  jz      short loc_18004C138
0x18004c132  call    cs:__imp_CloseServiceHandle
0x18004c138  mov     eax, ebx
0x18004c13a  jmp     loc_18004C2A0
0x18004c13f  mov     rbx, [rsp+88h+hSCObject]
0x18004c147  lea     r8, stru_1800F8688; struct SC_HANDLE__ *
0x18004c14e  mov     rdx, rbx; struct SC_HANDLE__ **
0x18004c151  lea     rcx, [rsp+88h+hService]; this
0x18004c159  mov     r9d, 16h; unsigned __int16 *
0x18004c15f  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEBGK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,ushort const *,ulong)
0x18004c164  mov     edi, eax
0x18004c166  test    eax, eax
0x18004c168  jns     short loc_18004C1C3
0x18004c16a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c171  lea     rsi, WPP_GLOBAL_Control
0x18004c178  cmp     rcx, rsi
0x18004c17b  jz      short loc_18004C19B
0x18004c17d  test    byte ptr [rcx+1Ch], 1
0x18004c181  jz      short loc_18004C19B
0x18004c183  mov     rcx, [rcx+10h]
0x18004c187  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x18004c18e  mov     edx, 43h ; 'C'
0x18004c193  mov     r9d, eax
0x18004c196  call    WPP_SF_d
0x18004c19b  mov     rcx, [rsp+88h+hService]; hSCObject
0x18004c1a3  test    rcx, rcx
0x18004c1a6  jz      short loc_18004C1AE
0x18004c1a8  call    cs:__imp_CloseServiceHandle
0x18004c1ae  test    rbx, rbx
0x18004c1b1  jz      short loc_18004C1BC
0x18004c1b3  mov     rcx, rbx; hSCObject
0x18004c1b6  call    cs:__imp_CloseServiceHandle
0x18004c1bc  mov     eax, edi
0x18004c1be  jmp     loc_18004C2A0
0x18004c1c3  mov     rdi, [rsp+88h+hService]
0x18004c1cb  mov     r15, [r14+88h]
0x18004c1d2  mov     rcx, rdi; this
0x18004c1d5  call    ?HrStartService@CommonUtil@@YAJPEAUSC_HANDLE__@@_KPEBQEBG@Z; CommonUtil::HrStartService(SC_HANDLE__ *,unsigned __int64,ushort const * const *)
0x18004c1da  lea     rsi, WPP_GLOBAL_Control
0x18004c1e1  mov     ebp, eax
0x18004c1e3  test    eax, eax
0x18004c1e5  js      short loc_18004C224
0x18004c1e7  mov     rcx, rdi; hService
0x18004c1ea  mov     [rsp+88h+var_60], r15; unsigned __int16 *
0x18004c1ef  call    ?UtilWaitForServiceStatus@CommonUtil@@YAJPEAUSC_HANDLE__@@KKKKPEBUIWaitForServiceCancellation@1@@Z; CommonUtil::UtilWaitForServiceStatus(SC_HANDLE__ *,ulong,ulong,ulong,ulong,CommonUtil::IWaitForServiceCancellation const *)
0x18004c1f4  mov     ebp, eax
0x18004c1f6  test    eax, eax
0x18004c1f8  jns     short loc_18004C250
0x18004c1fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c201  cmp     rcx, rsi
0x18004c204  jz      short loc_18004C282
0x18004c206  test    byte ptr [rcx+1Ch], 1
0x18004c20a  jz      short loc_18004C22B
0x18004c20c  mov     rcx, [rcx+10h]
0x18004c210  lea     r8, WPP_16ffd3dfa2bc3d570eea8a4a30209ffe_Traceguids
0x18004c217  mov     edx, 13h
0x18004c21c  mov     r9d, eax
0x18004c21f  call    WPP_SF_d
0x18004c224  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c22b  cmp     rcx, rsi
0x18004c22e  jz      short loc_18004C282
0x18004c230  test    byte ptr [rcx+1Ch], 1
0x18004c234  jz      short loc_18004C282
0x18004c236  mov     edx, 44h ; 'D'
0x18004c23b  mov     rcx, [rcx+10h]
0x18004c23f  lea     r8, WPP_6848f87e6c0e3a88007018e1c8c89e20_Traceguids
0x18004c246  mov     r9d, ebp
0x18004c249  call    WPP_SF_d
0x18004c24e  jmp     short loc_18004C282
0x18004c250  mov     rcx, rdi; this
0x18004c253  call    ?HrChangeServiceConfig@CommonUtil@@YAJPEAUSC_HANDLE__@@KKKPEBG11111PEAK@Z; CommonUtil::HrChangeServiceConfig(SC_HANDLE__ *,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong *)
0x18004c258  mov     ebp, eax
0x18004c25a  test    eax, eax
0x18004c25c  jns     short loc_18004C277
0x18004c25e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c265  cmp     rcx, rsi
0x18004c268  jz      short loc_18004C282
0x18004c26a  test    byte ptr [rcx+1Ch], 1
0x18004c26e  jz      short loc_18004C282
0x18004c270  mov     edx, 45h ; 'E'
0x18004c275  jmp     short loc_18004C23B
0x18004c277  mov     dword ptr [r14+90h], 0
0x18004c282  test    rdi, rdi
0x18004c285  jz      short loc_18004C290
0x18004c287  mov     rcx, rdi; hSCObject
0x18004c28a  call    cs:__imp_CloseServiceHandle
0x18004c290  test    rbx, rbx
0x18004c293  jz      short loc_18004C29E
0x18004c295  mov     rcx, rbx; hSCObject
0x18004c298  call    cs:__imp_CloseServiceHandle
0x18004c29e  mov     eax, ebp
0x18004c2a0  mov     rbx, [rsp+88h+arg_0]
0x18004c2a8  add     rsp, 60h
0x18004c2ac  pop     r15
0x18004c2ae  pop     r14
0x18004c2b0  pop     rdi
0x18004c2b1  pop     rsi
0x18004c2b2  pop     rbp
0x18004c2b3  retn
```
