# CAudioDeviceManager::OnPropertyValueChanged(ushort const *,_tagpropertykey)

- ea: `0x18000a470`
- end: `0x18000a943`
- name: `?OnPropertyValueChanged@CAudioDeviceManager@@UEAAJPEBGU_tagpropertykey@@@Z`
- size: `1235`
- prototype: `__int64 __fastcall(CAudioDeviceManager *this, const unsigned __int16 *, struct _tagpropertykey *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180006b0c`
- `0x18000a470`
- `0x18000ab60`
- `0x18000bc9c`
- `0x180029024`
- `0x180034c5c`
- `0x18003edc0`
- `0x18003f780`
- `0x18003f7a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a5b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a5b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7ca`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000a7c0`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000a7c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a634`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a634`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a7f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a910`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a7f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAudioDeviceManager::OnPropertyValueChanged(
        CAudioDeviceManager *this,
        const unsigned __int16 *a2,
        struct _tagpropertykey *a3)
{
  const unsigned __int16 *v4; // rdi
  _QWORD *v6; // rbx
  DWORD v7; // ebp
  HANDLE ProcessHeap; // rax
  _DWORD *v10; // rax
  ULONG_PTR v11; // r14
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // r15
  _WORD *v14; // rax
  _WORD *v15; // r10
  int v16; // esi
  unsigned __int64 v17; // rcx
  _WORD *v18; // rdx
  __int64 v19; // r8
  _WORD *v20; // rax
  __int64 v21; // r9
  DWORD pid; // eax
  void *v23; // rcx
  void *v24; // rcx
  __int64 v25; // r15
  bool v26; // cf

  v4 = a2;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, (_DWORD)a3, (_DWORD)a2, a3->fmtid.Data1, a3->pid);
    v6 = WPP_GLOBAL_Control;
  }
  if ( memcmp_0(a3, &DEVPKEY_DeviceClass_IconPath, 0x10u)
    && memcmp_0(a3, &DEVPKEY_Device_DeviceDesc, 0x10u)
    && memcmp_0(a3, &DEVPKEY_Device_ContainerId, 0x10u)
    && memcmp_0(a3, &DEVPKEY_Device_DriverNodeStrongName, 0x10u)
    && memcmp_0(a3, &DEVPKEY_Device_MatchingDeviceId, 0x10u)
    && memcmp_0(a3, &PKEY_SWD_DeviceInterfaceId, 0x10u)
    && memcmp_0(a3, &PKEY_SWD_DeviceInterfaceId_Retained, 0x10u)
    || (v7 = a3->pid, v7 == 12) && !memcmp_0(a3, &PKEY_DeviceClass_IconPath, 0x10u)
    || v7 == 2 && !memcmp_0(a3, &PKEY_Device_DeviceDesc, 0x10u) )
  {
    ProcessHeap = GetProcessHeap();
    v10 = HeapAlloc(ProcessHeap, 0, 0x58u);
    v11 = (ULONG_PTR)v10;
    if ( !v10 )
      goto LABEL_35;
    *(_QWORD *)v10 = &MMNotification_Event::`vftable';
    v10[2] = 5;
    *((_QWORD *)v10 + 2) = 0;
    *((_QWORD *)v10 + 3) = 0;
    *((_QWORD *)v10 + 6) = 0;
    *((_QWORD *)v10 + 10) = this;
    if ( v4 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v4[v12] );
      v13 = v12 + 1;
      *((_QWORD *)v10 + 2) = 0;
      if ( v12 + 1 >= v12 && is_mul_ok(v13, 2u) )
      {
        v14 = CoTaskMemAlloc(2 * v13);
        *(_QWORD *)(v11 + 16) = v14;
        v15 = v14;
        if ( v14 )
          v16 = 0;
        else
          v16 = -2147024882;
        if ( v16 < 0 )
          goto LABEL_34;
        if ( (v14 || v12 == -1) && v13 <= 0x7FFFFFFF )
        {
          if ( v12 >= 0x7FFFFFFF )
          {
            if ( v12 != -1 )
              *v14 = 0;
          }
          else
          {
            v17 = v12 + 1;
            v18 = v14;
            v19 = 0;
            do
            {
              if ( !v12 )
                break;
              if ( !*v4 )
                break;
              *v18++ = *v4++;
              --v12;
              ++v19;
              --v17;
            }
            while ( v17 );
            v20 = v18 - 1;
            v21 = v19 - 1;
            if ( v17 )
            {
              v20 = v18;
              v21 = v19;
            }
            *v20 = 0;
            if ( v17 )
            {
              v26 = v13 == v21;
              v25 = v13 - v21;
              if ( !v26 && v25 != 1 && (unsigned __int64)(2 * v25) > 2 )
                memset_0(&v15[v21 + 1], 0, 2 * v25 - 2);
            }
          }
        }
        else
        {
          *v14 = 0;
        }
      }
      else
      {
        v16 = -2147024362;
      }
      if ( v16 < 0 )
      {
LABEL_34:
        MMNotification_Event::`scalar deleting destructor'((MMNotification_Event *)v11, 1u);
LABEL_35:
        v11 = 0;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return 0;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
LABEL_45:
        if ( v11 && !PostQueuedCompletionStatus(g_WorkerEventPort, 0, v11, 0) )
        {
          GetLastError();
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
          }
          v23 = *(void **)(v11 + 16);
          *(_QWORD *)v11 = &MMNotification_Event::`vftable';
          if ( v23 )
          {
            CoTaskMemFree(v23);
            *(_QWORD *)(v11 + 16) = 0;
          }
          v24 = *(void **)(v11 + 24);
          if ( v24 )
          {
            CoTaskMemFree(v24);
            *(_QWORD *)(v11 + 24) = 0;
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v11 + 48);
          *(_QWORD *)v11 = &WORKER_THREAD_EVENT::`vftable';
          operator delete((void *)v11, 0x58u);
        }
        return 0;
      }
    }
    pid = a3->pid;
    *(GUID *)(v11 + 56) = a3->fmtid;
    *(_DWORD *)(v11 + 72) = pid;
    goto LABEL_45;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x80000) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_(v6[2], 35, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000a470  push    rbx
0x18000a472  push    rsi
0x18000a473  push    rdi
0x18000a474  push    r12
0x18000a476  push    r15
0x18000a478  sub     rsp, 30h
0x18000a47c  mov     r12, r8
0x18000a47f  mov     rdi, rdx
0x18000a482  mov     rsi, rcx
0x18000a485  mov     rbx, cs:WPP_GLOBAL_Control
0x18000a48c  lea     r15, WPP_GLOBAL_Control
0x18000a493  cmp     rbx, r15
0x18000a496  jnz     loc_18000A732
0x18000a49c  mov     r8d, 10h; Size
0x18000a4a2  mov     [rsp+58h+arg_0], rbp
0x18000a4a7  lea     rdx, DEVPKEY_DeviceClass_IconPath; Buf2
0x18000a4ae  mov     rcx, r12; Buf1
0x18000a4b1  call    memcmp_0
0x18000a4b6  test    eax, eax
0x18000a4b8  jz      short loc_18000A4D3
0x18000a4ba  mov     r8d, 10h; Size
0x18000a4c0  lea     rdx, DEVPKEY_Device_DeviceDesc; Buf2
0x18000a4c7  mov     rcx, r12; Buf1
0x18000a4ca  call    memcmp_0
0x18000a4cf  test    eax, eax
0x18000a4d1  jnz     short loc_18000A50F
0x18000a4d3  mov     ebp, [r12+10h]
0x18000a4d8  cmp     ebp, 0Ch
0x18000a4db  jz      loc_18000A869
0x18000a4e1  cmp     ebp, 2
0x18000a4e4  jz      loc_18000A88B
0x18000a4ea  cmp     rbx, r15
0x18000a4ed  jz      short loc_18000A4FC
0x18000a4ef  test    dword ptr [rbx+1Ch], 80000h
0x18000a4f6  jnz     loc_18000A91F
0x18000a4fc  xor     eax, eax
0x18000a4fe  mov     rbp, [rsp+58h+arg_0]
0x18000a503  add     rsp, 30h
0x18000a507  pop     r15
0x18000a509  pop     r12
0x18000a50b  pop     rdi
0x18000a50c  pop     rsi
0x18000a50d  pop     rbx
0x18000a50e  retn
0x18000a50f  mov     r8d, 10h; Size
0x18000a515  lea     rdx, DEVPKEY_Device_ContainerId; Buf2
0x18000a51c  mov     rcx, r12; Buf1
0x18000a51f  call    memcmp_0
0x18000a524  test    eax, eax
0x18000a526  jz      short loc_18000A4D3
0x18000a528  mov     r8d, 10h; Size
0x18000a52e  lea     rdx, DEVPKEY_Device_DriverNodeStrongName; Buf2
0x18000a535  mov     rcx, r12; Buf1
0x18000a538  call    memcmp_0
0x18000a53d  test    eax, eax
0x18000a53f  jz      short loc_18000A4D3
0x18000a541  mov     r8d, 10h; Size
0x18000a547  lea     rdx, DEVPKEY_Device_MatchingDeviceId; Buf2
0x18000a54e  mov     rcx, r12; Buf1
0x18000a551  call    memcmp_0
0x18000a556  test    eax, eax
0x18000a558  jz      loc_18000A4D3
0x18000a55e  mov     r8d, 10h; Size
0x18000a564  lea     rdx, PKEY_SWD_DeviceInterfaceId; Buf2
0x18000a56b  mov     rcx, r12; Buf1
0x18000a56e  call    memcmp_0
0x18000a573  test    eax, eax
0x18000a575  jz      loc_18000A4D3
0x18000a57b  mov     r8d, 10h; Size
0x18000a581  lea     rdx, PKEY_SWD_DeviceInterfaceId_Retained; Buf2
0x18000a588  mov     rcx, r12; Buf1
0x18000a58b  call    memcmp_0
0x18000a590  test    eax, eax
0x18000a592  jz      loc_18000A4D3
0x18000a598  mov     [rsp+58h+arg_8], r13
0x18000a59d  mov     [rsp+58h+arg_18], r14
0x18000a5a2  call    cs:__imp_GetProcessHeap
0x18000a5a8  xor     edx, edx; dwFlags
0x18000a5aa  mov     r8d, 58h ; 'X'; dwBytes
0x18000a5b0  mov     rcx, rax; hHeap
0x18000a5b3  call    cs:__imp_HeapAlloc
0x18000a5b9  xor     ebp, ebp
0x18000a5bb  mov     [rsp+58h+arg_10], rax
0x18000a5c0  lea     r13, ??_7MMNotification_Event@@6B@; const MMNotification_Event::`vftable'
0x18000a5c7  mov     r14, rax
0x18000a5ca  test    rax, rax
0x18000a5cd  jz      loc_18000A72B
0x18000a5d3  mov     [rax], r13
0x18000a5d6  mov     dword ptr [rax+8], 5
0x18000a5dd  mov     [rax+10h], rbp
0x18000a5e1  mov     [rax+18h], rbp
0x18000a5e5  mov     [rax+30h], rbp
0x18000a5e9  mov     [rax+50h], rsi
0x18000a5ed  test    rax, rax
0x18000a5f0  jz      loc_18000A72B
0x18000a5f6  test    rdi, rdi
0x18000a5f9  jz      loc_18000A77C
0x18000a5ff  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a606  inc     rbx
0x18000a609  cmp     [rdi+rbx*2], bp
0x18000a60d  jnz     short loc_18000A606
0x18000a60f  lea     r15, [rbx+1]
0x18000a613  mov     [rax+10h], rbp
0x18000a617  cmp     r15, rbx
0x18000a61a  jb      loc_18000A724
0x18000a620  mov     eax, 2
0x18000a625  mul     r15
0x18000a628  test    rdx, rdx
0x18000a62b  jnz     loc_18000A724
0x18000a631  mov     rcx, rax; cb
0x18000a634  call    cs:__imp_CoTaskMemAlloc
0x18000a63a  mov     [r14+10h], rax
0x18000a63e  mov     r10, rax
0x18000a641  test    rax, rax
0x18000a644  jnz     loc_18000A830
0x18000a64a  mov     esi, 8007000Eh
0x18000a64f  test    esi, esi
0x18000a651  js      short loc_18000A6CC
0x18000a653  test    r10, r10
0x18000a656  jz      loc_18000A8AD
0x18000a65c  cmp     r15, 7FFFFFFFh
0x18000a663  ja      loc_18000A8B6
0x18000a669  cmp     rbx, 7FFFFFFFh
0x18000a670  jnb     loc_18000A8BE
0x18000a676  test    r15, r15
0x18000a679  jz      short loc_18000A6C4
0x18000a67b  mov     rcx, r15
0x18000a67e  mov     rdx, r10
0x18000a681  mov     r8, rbp
0x18000a684  test    rbx, rbx
0x18000a687  jz      short loc_18000A6A8
0x18000a689  movzx   eax, word ptr [rdi]
0x18000a68c  test    ax, ax
0x18000a68f  jz      short loc_18000A6A8
0x18000a691  mov     [rdx], ax
0x18000a694  add     rdi, 2
0x18000a698  add     rdx, 2
0x18000a69c  dec     rbx
0x18000a69f  inc     r8
0x18000a6a2  sub     rcx, 1
0x18000a6a6  jnz     short loc_18000A684
0x18000a6a8  test    rcx, rcx
0x18000a6ab  lea     rax, [rdx-2]
0x18000a6af  lea     r9, [r8-1]
0x18000a6b3  cmovnz  rax, rdx
0x18000a6b7  cmovnz  r9, r8
0x18000a6bb  mov     [rax], bp
0x18000a6be  jnz     loc_18000A837
0x18000a6c4  test    esi, esi
0x18000a6c6  jns     loc_18000A775
0x18000a6cc  mov     edx, 1; unsigned int
0x18000a6d1  mov     rcx, r14; this
0x18000a6d4  call    ??_GMMNotification_Event@@UEAAPEAXI@Z; MMNotification_Event::`scalar deleting destructor'(uint)
0x18000a6d9  lea     r15, WPP_GLOBAL_Control
0x18000a6e0  mov     r14, rbp
0x18000a6e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6ea  cmp     rcx, r15
0x18000a6ed  jz      loc_18000A794
0x18000a6f3  test    dword ptr [rcx+1Ch], 80000h
0x18000a6fa  jz      loc_18000A78F
0x18000a700  cmp     byte ptr [rcx+19h], 2
0x18000a704  jb      loc_18000A78F
0x18000a70a  mov     rcx, [rcx+10h]
0x18000a70e  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x18000a715  mov     edx, 24h ; '$'
0x18000a71a  mov     r9d, esi
0x18000a71d  call    WPP_SF_d
0x18000a722  jmp     short loc_18000A78F
0x18000a724  mov     esi, 80070216h
0x18000a729  jmp     short loc_18000A6C4
0x18000a72b  mov     esi, 8007000Eh
0x18000a730  jmp     short loc_18000A6E0
0x18000a732  test    dword ptr [rbx+1Ch], 80000h
0x18000a739  jz      loc_18000A49C
0x18000a73f  cmp     byte ptr [rbx+19h], 5
0x18000a743  jb      loc_18000A49C
0x18000a749  mov     eax, [r8+10h]
0x18000a74d  mov     edx, 22h ; '"'
0x18000a752  mov     rcx, [rbx+10h]
0x18000a756  mov     r9, rdi
0x18000a759  mov     [rsp+58h+var_30], eax
0x18000a75d  mov     eax, [r8]
0x18000a760  mov     [rsp+58h+var_38], eax
0x18000a764  call    WPP_SF_SDd
0x18000a769  mov     rbx, cs:WPP_GLOBAL_Control
0x18000a770  jmp     loc_18000A49C
0x18000a775  lea     r15, WPP_GLOBAL_Control
0x18000a77c  movups  xmm0, xmmword ptr [r12]
0x18000a781  mov     eax, [r12+10h]
0x18000a786  movups  xmmword ptr [r14+38h], xmm0
0x18000a78b  mov     [r14+48h], eax
0x18000a78f  test    r14, r14
0x18000a792  jnz     short loc_18000A7B1
0x18000a794  mov     r13, [rsp+58h+arg_8]
0x18000a799  xor     eax, eax
0x18000a79b  mov     r14, [rsp+58h+arg_18]
0x18000a7a0  mov     rbp, [rsp+58h+arg_0]
0x18000a7a5  add     rsp, 30h
0x18000a7a9  pop     r15
0x18000a7ab  pop     r12
0x18000a7ad  pop     rdi
0x18000a7ae  pop     rsi
0x18000a7af  pop     rbx
0x18000a7b0  retn
0x18000a7b1  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; CompletionPort
0x18000a7b8  xor     r9d, r9d; lpOverlapped
0x18000a7bb  mov     r8, r14; dwCompletionKey
0x18000a7be  xor     edx, edx; dwNumberOfBytesTransferred
0x18000a7c0  call    cs:__imp_PostQueuedCompletionStatus
0x18000a7c6  test    eax, eax
0x18000a7c8  jnz     short loc_18000A794
0x18000a7ca  call    cs:__imp_GetLastError
0x18000a7d0  test    eax, eax
0x18000a7d2  jg      loc_18000A8CF
0x18000a7d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7df  cmp     rcx, r15
0x18000a7e2  jnz     loc_18000A8DC
0x18000a7e8  mov     rcx, [r14+10h]; pv
0x18000a7ec  mov     [r14], r13
0x18000a7ef  test    rcx, rcx
0x18000a7f2  jz      short loc_18000A7FE
0x18000a7f4  call    cs:__imp_CoTaskMemFree
0x18000a7fa  mov     [r14+10h], rbp
0x18000a7fe  mov     rcx, [r14+18h]; pv
0x18000a802  test    rcx, rcx
0x18000a805  jnz     loc_18000A910
0x18000a80b  lea     rcx, [r14+30h]
0x18000a80f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000a814  lea     rax, ??_7WORKER_THREAD_EVENT@@6B@; const WORKER_THREAD_EVENT::`vftable'
0x18000a81b  mov     edx, 58h ; 'X'; unsigned __int64
0x18000a820  mov     rcx, r14; void *
0x18000a823  mov     [r14], rax
0x18000a826  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a82b  jmp     loc_18000A794
0x18000a830  mov     esi, ebp
0x18000a832  jmp     loc_18000A64F
0x18000a837  sub     r15, r9
0x18000a83a  cmp     r15, 1
0x18000a83e  jbe     loc_18000A6C4
0x18000a844  lea     r8, [r15+r15]
0x18000a848  cmp     r8, 2
0x18000a84c  jbe     loc_18000A6C4
0x18000a852  inc     r9
0x18000a855  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000a859  xor     edx, edx; Val
0x18000a85b  lea     rcx, [r10+r9*2]; void *
0x18000a85f  call    memset_0
0x18000a864  jmp     loc_18000A6C4
0x18000a869  mov     r8d, 10h; Size
0x18000a86f  lea     rdx, PKEY_DeviceClass_IconPath; Buf2
0x18000a876  mov     rcx, r12; Buf1
0x18000a879  call    memcmp_0
0x18000a87e  test    eax, eax
0x18000a880  jz      loc_18000A598
0x18000a886  jmp     loc_18000A4E1
0x18000a88b  mov     r8d, 10h; Size
0x18000a891  lea     rdx, PKEY_Device_DeviceDesc; Buf2
0x18000a898  mov     rcx, r12; Buf1
0x18000a89b  call    memcmp_0
0x18000a8a0  test    eax, eax
0x18000a8a2  jnz     loc_18000A4EA
0x18000a8a8  jmp     loc_18000A598
0x18000a8ad  test    r15, r15
0x18000a8b0  jz      loc_18000A65C
0x18000a8b6  mov     [rax], bp
0x18000a8b9  jmp     loc_18000A6C4
0x18000a8be  test    r15, r15
0x18000a8c1  jz      loc_18000A6C4
0x18000a8c7  mov     [rax], bp
0x18000a8ca  jmp     loc_18000A6C4
0x18000a8cf  movzx   eax, ax
0x18000a8d2  or      eax, 80070000h
0x18000a8d7  jmp     loc_18000A7D8
0x18000a8dc  test    dword ptr [rcx+1Ch], 80000h
0x18000a8e3  jz      loc_18000A7E8
0x18000a8e9  cmp     byte ptr [rcx+19h], 2
0x18000a8ed  jb      loc_18000A7E8
0x18000a8f3  mov     rcx, [rcx+10h]
0x18000a8f7  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x18000a8fe  mov     edx, 25h ; '%'
0x18000a903  mov     r9d, eax
0x18000a906  call    WPP_SF_d
0x18000a90b  jmp     loc_18000A7E8
0x18000a910  call    cs:__imp_CoTaskMemFree
0x18000a916  mov     [r14+18h], rbp
0x18000a91a  jmp     loc_18000A80B
0x18000a91f  cmp     byte ptr [rbx+19h], 4
0x18000a923  jb      loc_18000A4FC
0x18000a929  mov     rcx, [rbx+10h]
0x18000a92d  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x18000a934  mov     edx, 23h ; '#'
0x18000a939  call    WPP_SF_
0x18000a93e  jmp     loc_18000A4FC
```
