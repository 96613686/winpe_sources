# CLocationMovementDetector::UnregisterForMovementNotifications(ILocationMovementDetectorSink *)

- ea: `0x18001bb80`
- end: `0x18001be01`
- name: `?UnregisterForMovementNotifications@CLocationMovementDetector@@UEAAJPEAUILocationMovementDetectorSink@@@Z`
- size: `641`
- prototype: `__int64 __fastcall(CLocationMovementDetector *__hidden this, struct ILocationMovementDetectorSink *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180012194`
- `0x180012398`
- `0x18001bb80`
- `0x18001be08`
- `0x18001be3c`
- `0x18001bee4`
- `0x18001c004`
- `0x1800831e0`
- `0x18009c310`
- `0x1800a98c0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bd69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bd69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bbba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bbba`

## string_xrefs

- `0x18001bd04`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationmovementdetector.cpp`
- `0x18001bd3d`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationmovementdetector.cpp`
- `0x18001bdb8`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationmovementdetector.cpp`
- `0x18001bcfd`: `CLocationMovementDetector::UnregisterForMovementNotifications`
- `0x18001bd36`: `CLocationMovementDetector::UnregisterForMovementNotifications`
- `0x18001bdb1`: `CLocationMovementDetector::UnregisterForMovementNotifications`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLocationMovementDetector::UnregisterForMovementNotifications(
        CLocationMovementDetector *this,
        struct ILocationMovementDetectorSink *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  _QWORD *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rcx
  bool v8; // r15
  int v9; // eax
  int v10; // eax
  unsigned int v11; // ebx
  wil::details *v13; // [rsp+28h] [rbp-50h]
  int v14[2]; // [rsp+30h] [rbp-48h] BYREF
  char *v15; // [rsp+38h] [rbp-40h] BYREF
  char v16; // [rsp+40h] [rbp-38h]
  wil::details::in1diag5 *retaddr; // [rsp+78h] [rbp+0h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 376);
  v15 = (char *)this + 376;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 376));
  v16 = 1;
  if ( !a2 )
  {
    v11 = -2147467261;
    LODWORD(v13) = -2147467261;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x200,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationmovementdetector.cpp",
      "CLocationMovementDetector::UnregisterForMovementNotifications",
      "pSink",
      v13,
      v14[0]);
LABEL_19:
    LeaveCriticalSection(v4);
    return v11;
  }
  if ( !*((_DWORD *)this + 26) )
  {
    v5 = (_QWORD *)*((_QWORD *)this + 14);
    while ( 1 )
    {
      v5 = (_QWORD *)*v5;
      if ( v5 == *((_QWORD **)this + 14) )
        break;
      v6 = v5[2];
      if ( v6 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 8LL))(v5[2]);
        *(_QWORD *)v14 = 0;
        v15 = 0;
        (**(void (__fastcall ***)(__int64, GUID *, int *))v6)(v6, &GUID_00000000_0000_0000_c000_000000000046, v14);
        (**(void (__fastcall ***)(struct ILocationMovementDetectorSink *, GUID *, char **))a2)(
          a2,
          &GUID_00000000_0000_0000_c000_000000000046,
          &v15);
        v7 = *(_QWORD *)v14;
        v8 = *(_QWORD *)v14 == (_QWORD)v15;
        if ( v15 )
        {
          (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))(v15);
          v7 = *(_QWORD *)v14;
        }
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      else
      {
        v8 = 0;
      }
      if ( v8 )
      {
        *(_QWORD *)v5[1] = *v5;
        *(_QWORD *)(*v5 + 8LL) = v5[1];
        --*((_QWORD *)this + 15);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v5 + 2);
        std::_Deallocate<16>(v5, 0x18u);
        if ( !*((_QWORD *)this + 15) )
        {
          CLocationActivityDetector::StopTracking((CLocationMovementDetector *)((char *)this + 600));
          v9 = CLocationMovementDetector::StopWifiMonitoring(this);
          if ( v9 < 0 )
          {
            LODWORD(v13) = v9;
            wil::details::in1diag5::_Log_Hr(
              retaddr,
              (void *)0x20F,
              (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationmovementdetector.cpp",
              "CLocationMovementDetector::UnregisterForMovementNotifications",
              "StopWifiMonitoring()",
              (const char *)v13,
              v14[0]);
          }
          v10 = CLocationMovementDetector::StopCellMonitoring(this);
          if ( v10 < 0 )
          {
            LODWORD(v13) = v10;
            wil::details::in1diag5::_Log_Hr(
              retaddr,
              (void *)0x210,
              (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationmovementdetector.cpp",
              "CLocationMovementDetector::UnregisterForMovementNotifications",
              "StopCellMonitoring()",
              (const char *)v13,
              v14[0]);
          }
        }
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        break;
      }
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    v11 = 0;
    goto LABEL_19;
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v15);
  return 2147500036LL;
}

```

## disassembly

```asm
0x18001bb80  mov     [rsp+arg_10], rbx
0x18001bb85  mov     [rsp+arg_18], rbp
0x18001bb8a  push    rsi
0x18001bb8b  push    rdi
0x18001bb8c  push    r12
0x18001bb8e  push    r14
0x18001bb90  push    r15
0x18001bb92  sub     rsp, 50h
0x18001bb96  mov     rax, cs:__security_cookie
0x18001bb9d  xor     rax, rsp
0x18001bba0  mov     [rsp+78h+var_30], rax
0x18001bba5  mov     r12, rdx
0x18001bba8  mov     rsi, rcx
0x18001bbab  lea     rbp, [rcx+178h]
0x18001bbb2  mov     [rsp+78h+var_40], rbp
0x18001bbb7  mov     rcx, rbp; lpCriticalSection
0x18001bbba  call    cs:__imp_EnterCriticalSection
0x18001bbc0  mov     [rsp+78h+var_38], 1
0x18001bbc5  test    r12, r12
0x18001bbc8  jz      loc_18001BD97
0x18001bbce  cmp     dword ptr [rsi+68h], 0
0x18001bbd2  jnz     loc_18001BDED
0x18001bbd8  mov     rbx, [rsi+70h]
0x18001bbdc  mov     rbx, [rbx]
0x18001bbdf  cmp     rbx, [rsi+70h]
0x18001bbe3  jz      loc_18001BD64
0x18001bbe9  mov     rdi, [rbx+10h]
0x18001bbed  test    rdi, rdi
0x18001bbf0  jz      short loc_18001BC02
0x18001bbf2  mov     rax, [rdi]
0x18001bbf5  mov     rcx, rdi
0x18001bbf8  mov     rax, [rax+8]
0x18001bbfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc01  nop
0x18001bc02  test    rdi, rdi
0x18001bc05  jz      loc_18001BDCB
0x18001bc0b  mov     qword ptr [rsp+78h+var_48], 0; int
0x18001bc14  mov     [rsp+78h+var_40], 0
0x18001bc1d  mov     rax, [rdi]
0x18001bc20  lea     r8, [rsp+78h+var_48]
0x18001bc25  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001bc2c  mov     rcx, rdi
0x18001bc2f  mov     rax, [rax]
0x18001bc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc37  mov     rax, [r12]
0x18001bc3b  lea     r8, [rsp+78h+var_40]
0x18001bc40  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001bc47  mov     rcx, r12
0x18001bc4a  mov     rax, [rax]
0x18001bc4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc52  mov     rcx, qword ptr [rsp+78h+var_48]
0x18001bc57  mov     rax, [rsp+78h+var_40]
0x18001bc5c  cmp     rcx, rax
0x18001bc5f  setz    r15b
0x18001bc63  test    rax, rax
0x18001bc66  jz      short loc_18001BC7F
0x18001bc68  mov     rcx, [rax]
0x18001bc6b  mov     rdx, [rcx+10h]
0x18001bc6f  mov     rcx, rax
0x18001bc72  mov     rax, rdx
0x18001bc75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc7a  mov     rcx, qword ptr [rsp+78h+var_48]
0x18001bc7f  test    rcx, rcx
0x18001bc82  jz      short loc_18001BC91
0x18001bc84  mov     rax, [rcx]
0x18001bc87  mov     rax, [rax+10h]
0x18001bc8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc90  nop
0x18001bc91  test    r15b, r15b
0x18001bc94  jz      loc_18001BDD3
0x18001bc9a  mov     rdx, [rbx+8]
0x18001bc9e  mov     rax, [rbx]
0x18001bca1  mov     [rdx], rax
0x18001bca4  mov     rdx, [rbx]
0x18001bca7  mov     rax, [rbx+8]
0x18001bcab  mov     [rdx+8], rax
0x18001bcaf  dec     qword ptr [rsi+78h]
0x18001bcb3  lea     rcx, [rbx+10h]
0x18001bcb7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001bcbc  mov     edx, 18h
0x18001bcc1  mov     rcx, rbx
0x18001bcc4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001bcc9  cmp     qword ptr [rsi+78h], 0
0x18001bcce  jnz     short loc_18001BD4F
0x18001bcd0  lea     rcx, [rsi+258h]; this
0x18001bcd7  call    ?StopTracking@CLocationActivityDetector@@QEAAXXZ; CLocationActivityDetector::StopTracking(void)
0x18001bcdc  mov     rcx, rsi; this
0x18001bcdf  call    ?StopWifiMonitoring@CLocationMovementDetector@@QEAAJXZ; CLocationMovementDetector::StopWifiMonitoring(void)
0x18001bce4  mov     rcx, [rsp+78h]; this
0x18001bce9  test    eax, eax
0x18001bceb  jns     short loc_18001BD15
0x18001bced  mov     dword ptr [rsp+78h+var_50], eax; char *
0x18001bcf1  lea     rax, aStopwifimonito; "StopWifiMonitoring()"
0x18001bcf8  mov     [rsp+78h+var_58], rax; char *
0x18001bcfd  lea     r9, aClocationmovem_0; "CLocationMovementDetector::UnregisterFo"...
0x18001bd04  lea     r8, aOnecoreuapDriv_65; "onecoreuap\\drivers\\mobilepc\\location"...
0x18001bd0b  mov     edx, 20Fh; void *
0x18001bd10  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18001bd15  mov     rcx, rsi; this
0x18001bd18  call    ?StopCellMonitoring@CLocationMovementDetector@@QEAAJXZ; CLocationMovementDetector::StopCellMonitoring(void)
0x18001bd1d  mov     rcx, [rsp+78h]; this
0x18001bd22  test    eax, eax
0x18001bd24  jns     short loc_18001BD4F
0x18001bd26  mov     dword ptr [rsp+78h+var_50], eax; char *
0x18001bd2a  lea     rax, aStopcellmonito; "StopCellMonitoring()"
0x18001bd31  mov     [rsp+78h+var_58], rax; char *
0x18001bd36  lea     r9, aClocationmovem_0; "CLocationMovementDetector::UnregisterFo"...
0x18001bd3d  lea     r8, aOnecoreuapDriv_65; "onecoreuap\\drivers\\mobilepc\\location"...
0x18001bd44  mov     edx, 210h; void *
0x18001bd49  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18001bd4e  nop
0x18001bd4f  test    rdi, rdi
0x18001bd52  jz      short loc_18001BD64
0x18001bd54  mov     rax, [rdi]
0x18001bd57  mov     rcx, rdi
0x18001bd5a  mov     rax, [rax+10h]
0x18001bd5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd63  nop
0x18001bd64  xor     ebx, ebx
0x18001bd66  mov     rcx, rbp; lpCriticalSection
0x18001bd69  call    cs:__imp_LeaveCriticalSection
0x18001bd6f  mov     eax, ebx
0x18001bd71  mov     rcx, [rsp+78h+var_30]
0x18001bd76  xor     rcx, rsp; StackCookie
0x18001bd79  call    __security_check_cookie
0x18001bd7e  lea     r11, [rsp+78h+var_28]
0x18001bd83  mov     rbx, [r11+40h]
0x18001bd87  mov     rbp, [r11+48h]
0x18001bd8b  mov     rsp, r11
0x18001bd8e  pop     r15
0x18001bd90  pop     r14
0x18001bd92  pop     r12
0x18001bd94  pop     rdi
0x18001bd95  pop     rsi
0x18001bd96  retn
0x18001bd97  mov     rcx, [rsp+78h]; this
0x18001bd9c  mov     ebx, 80004003h
0x18001bda1  mov     dword ptr [rsp+78h+var_50], ebx; wil::details *
0x18001bda5  lea     rax, aPsink; "pSink"
0x18001bdac  mov     [rsp+78h+var_58], rax; char *
0x18001bdb1  lea     r9, aClocationmovem_0; "CLocationMovementDetector::UnregisterFo"...
0x18001bdb8  lea     r8, aOnecoreuapDriv_65; "onecoreuap\\drivers\\mobilepc\\location"...
0x18001bdbf  mov     edx, 200h; void *
0x18001bdc4  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18001bdc9  jmp     short loc_18001BD66
0x18001bdcb  xor     r15b, r15b
0x18001bdce  jmp     loc_18001BC91
0x18001bdd3  test    rdi, rdi
0x18001bdd6  jz      short loc_18001BDE8
0x18001bdd8  mov     rax, [rdi]
0x18001bddb  mov     rcx, rdi
0x18001bdde  mov     rax, [rax+10h]
0x18001bde2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bde7  nop
0x18001bde8  jmp     loc_18001BBDC
0x18001bded  lea     rcx, [rsp+78h+var_40]
0x18001bdf2  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001bdf7  mov     eax, 80004004h
0x18001bdfc  jmp     loc_18001BD71
```
