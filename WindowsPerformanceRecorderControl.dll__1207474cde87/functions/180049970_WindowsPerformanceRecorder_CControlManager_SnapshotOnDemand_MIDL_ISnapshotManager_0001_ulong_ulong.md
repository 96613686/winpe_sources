# WindowsPerformanceRecorder::CControlManager::SnapshotOnDemand(__MIDL_ISnapshotManager_0001,ulong *,ulong)

- ea: `0x180049970`
- end: `0x180049c93`
- name: `?SnapshotOnDemand@CControlManager@WindowsPerformanceRecorder@@UEAAJW4__MIDL_ISnapshotManager_0001@@PEAKK@Z`
- size: `803`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18001a92c`
- `0x18001c8bc`
- `0x18001e6e0`
- `0x1800248d8`
- `0x180040a04`
- `0x180049970`
- `0x18004ece0`
- `0x18004ed10`
- `0x18006264c`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180049a5d`
- `OLEAUT32!__imp_SysFreeString` at `0x180049b05`
- `OLEAUT32!__imp_SysFreeString` at `0x180049bff`
- `OLEAUT32!__imp_SysFreeString` at `0x180049c31`
- `OLEAUT32!__imp_SysFreeString` at `0x180049c66`
- `OLEAUT32!__imp_SysFreeString` at `0x180049a5d`
- `OLEAUT32!__imp_SysFreeString` at `0x180049b05`
- `OLEAUT32!__imp_SysFreeString` at `0x180049bff`
- `OLEAUT32!__imp_SysFreeString` at `0x180049c31`
- `OLEAUT32!__imp_SysFreeString` at `0x180049c66`

## string_xrefs

- `0x180049a16`: `COMGUARD`
- `0x180049ab3`: `COMGUARD`
- `0x180049bb1`: `COMGUARD`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::SnapshotOnDemand(
        __int64 a1,
        int a2,
        char *a3,
        unsigned int a4)
{
  __int64 v4; // r12
  unsigned int v5; // ebx
  struct WindowsPerformanceRecorder::CControlManager *v6; // rdi
  signed int v7; // eax
  _QWORD *v9; // rbx
  signed int v10; // eax
  unsigned int v11; // edi
  WindowsPerformanceRecorder::CETWProperties *v12; // r15
  WindowsPerformanceRecorder::CETWProperties *v13; // rax
  __int64 v14; // r13
  _QWORD *i; // rdi
  __int64 v16; // rax
  signed int v17; // r12d
  unsigned int Format; // [rsp+20h] [rbp-B8h]
  char *v19; // [rsp+28h] [rbp-B0h]
  char *v20; // [rsp+28h] [rbp-B0h]
  unsigned int v22; // [rsp+40h] [rbp-98h]
  struct IProfileCollection *v23; // [rsp+48h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-88h] BYREF
  void (__fastcall ***v25)(_QWORD, __int64); // [rsp+58h] [rbp-80h]
  WindowsPerformanceRecorder::CETWProperties *v26; // [rsp+60h] [rbp-78h]
  char *v27; // [rsp+68h] [rbp-70h]
  __int64 v28; // [rsp+70h] [rbp-68h]
  __int64 v29; // [rsp+78h] [rbp-60h]
  ATL::CAtlException *v30; // [rsp+80h] [rbp-58h] BYREF
  struct _GUID v31; // [rsp+88h] [rbp-50h] BYREF

  v29 = -2;
  v27 = a3;
  v4 = a1;
  v28 = a1;
  bstrString = 0;
  v23 = 0;
  if ( a2 != 1 )
  {
    v5 = -2147024809;
LABEL_9:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    SysFreeString(bstrString);
    return v5;
  }
  v31 = (struct _GUID)HeapSnapGuid;
  if ( a4 > 8 )
  {
    v5 = -984068077;
    goto LABEL_9;
  }
  v6 = (struct WindowsPerformanceRecorder::CControlManager *)(a1 - 208);
  v7 = WindowsPerformanceRecorder::CControlManager::QueryRunningProfile(
         (WindowsPerformanceRecorder::CControlManager *)(a1 - 208),
         1,
         &bstrString,
         0,
         &v23);
  v5 = v7;
  if ( v7 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "SnapshotOnDemand",
      (const char *)0x15A,
      v7,
      "COMGUARD",
      v19);
    goto LABEL_9;
  }
  if ( (*(_BYTE *)(v4 + 360) & 2) != 0 )
  {
    v5 = -984076288;
    goto LABEL_9;
  }
  try
  {
    v25 = 0;
    v26 = (WindowsPerformanceRecorder::CETWProperties *)operator new(0x1A8u);
    v9 = (_QWORD *)WindowsPerformanceRecorder::CETWProperties::CETWProperties(v26);
    v25 = (void (__fastcall ***)(_QWORD, __int64))v9;
    v10 = WindowsPerformanceRecorder::CETWProperties::Initialize(
            (WindowsPerformanceRecorder::CETWProperties *)v9,
            v23,
            v6,
            (*(_DWORD *)(v4 + 360) & 0x10) != 0);
  }
  catch ( ATL::CAtlException *v30 )
  {
    v22 = *(_DWORD *)v30;
    if ( v25 )
      (**v25)(v25, 1);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    SysFreeString(bstrString);
    return v22;
  }
  v11 = v10;
  if ( v10 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "SnapshotOnDemand",
      (const char *)0x165,
      v10,
      "COMGUARD",
      v19);
    if ( v9 )
      (*(void (__fastcall **)(_QWORD *, __int64))*v9)(v9, 1);
    v25 = 0;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    SysFreeString(bstrString);
    return v11;
  }
  v12 = (WindowsPerformanceRecorder::CETWProperties *)v9[1];
  v13 = (WindowsPerformanceRecorder::CETWProperties *)v9[2];
  v26 = v13;
LABEL_15:
  if ( v12 != v13 )
  {
    v14 = *(_QWORD *)v12;
    for ( i = *(_QWORD **)(*(_QWORD *)v12 + 24LL); ; i += 33 )
    {
      if ( i == *(_QWORD **)(v14 + 32) )
      {
        v12 = (WindowsPerformanceRecorder::CETWProperties *)((char *)v12 + 8);
        v13 = v26;
        goto LABEL_15;
      }
      v16 = *i - *(_QWORD *)&v31.Data1;
      if ( *i == *(_QWORD *)&v31.Data1 )
        v16 = i[1] - *(_QWORD *)v31.Data4;
      if ( !v16 )
      {
        v17 = WindowsPerformanceRecorder::CControlManager::EnableSnapshotProviderOnSession(
                (WindowsPerformanceRecorder::CControlManager *)(v4 - 208),
                *(_QWORD *)(*(_QWORD *)(v4 + 184) + 8LL),
                &v31,
                0,
                Format,
                (unsigned int *)v27,
                a4,
                0);
        if ( v17 < 0 )
        {
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            "SnapshotOnDemand",
            (const char *)0x177,
            v17,
            "COMGUARD",
            v20);
          if ( v9 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v9)(v9, 1);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
          SysFreeString(bstrString);
          return (unsigned int)v17;
        }
        v4 = v28;
      }
    }
  }
  if ( v9 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v9)(v9, 1);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  SysFreeString(bstrString);
  return 0;
}

```

## disassembly

```asm
0x180049970  push    rbx
0x180049972  push    rsi
0x180049973  push    rdi
0x180049974  push    r12
0x180049976  push    r13
0x180049978  push    r14
0x18004997a  push    r15
0x18004997c  sub     rsp, 0A0h
0x180049983  mov     [rsp+0D8h+var_60], 0FFFFFFFFFFFFFFFEh
0x18004998c  mov     rax, cs:__security_cookie
0x180049993  xor     rax, rsp
0x180049996  mov     [rsp+0D8h+var_40], rax
0x18004999e  mov     [rsp+0D8h+var_98], r9d
0x1800499a3  mov     [rsp+0D8h+var_70], r8
0x1800499a8  mov     r12, rcx
0x1800499ab  mov     [rsp+0D8h+var_68], rcx
0x1800499b0  xor     esi, esi
0x1800499b2  mov     [rsp+0D8h+bstrString], rsi
0x1800499b7  mov     [rsp+0D8h+var_90], rsi
0x1800499bc  cmp     edx, 1
0x1800499bf  jz      short loc_1800499CB
0x1800499c1  mov     ebx, 80070057h
0x1800499c6  jmp     loc_180049A4D
0x1800499cb  movups  xmm0, cs:HeapSnapGuid
0x1800499d2  movdqu  xmmword ptr [rsp+0D8h+var_50.Data1], xmm0
0x1800499db  cmp     r9d, 8
0x1800499df  jbe     short loc_1800499E8
0x1800499e1  mov     ebx, 0C5585013h
0x1800499e6  jmp     short loc_180049A4D
0x1800499e8  lea     rdi, [rcx-0D0h]
0x1800499ef  lea     rax, [rsp+0D8h+var_90]
0x1800499f4  mov     [rsp+0D8h+Format], rax; unsigned int
0x1800499f9  xor     r9d, r9d; unsigned __int16 **
0x1800499fc  lea     r8, [rsp+0D8h+bstrString]; unsigned __int16 **
0x180049a01  lea     r14d, [r9+1]
0x180049a05  mov     dl, r14b; bool
0x180049a08  mov     rcx, rdi; this
0x180049a0b  call    ?QueryRunningProfile@CControlManager@WindowsPerformanceRecorder@@AEAAJ_NPEAPEAG1PEAPEAUIProfileCollection@@@Z; WindowsPerformanceRecorder::CControlManager::QueryRunningProfile(bool,ushort * *,ushort * *,IProfileCollection * *)
0x180049a10  mov     ebx, eax
0x180049a12  test    eax, eax
0x180049a14  jns     short loc_180049A3D
0x180049a16  lea     rax, aComguard; "COMGUARD"
0x180049a1d  mov     [rsp+0D8h+Format], rax; Format
0x180049a22  mov     r9d, ebx; unsigned int
0x180049a25  mov     r8d, 15Ah; char *
0x180049a2b  lea     rdx, aSnapshotondema; "SnapshotOnDemand"
0x180049a32  lea     ecx, [r14+1]; this
0x180049a36  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180049a3b  jmp     short loc_180049A4D
0x180049a3d  test    byte ptr [r12+168h], 2
0x180049a46  jz      short loc_180049A6A
0x180049a48  mov     ebx, 0C5583000h
0x180049a4d  lea     rcx, [rsp+0D8h+var_90]
0x180049a52  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180049a57  nop
0x180049a58  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x180049a5d  call    cs:__imp_SysFreeString
0x180049a63  mov     eax, ebx
0x180049a65  jmp     loc_180049C70
0x180049a6a  mov     [rsp+0D8h+var_80], rsi
0x180049a6f  mov     ecx, 1A8h; Size
0x180049a74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049a79  mov     [rsp+0D8h+var_78], rax
0x180049a7e  mov     rcx, rax; this
0x180049a81  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x180049a86  mov     rbx, rax
0x180049a89  mov     [rsp+0D8h+var_80], rax
0x180049a8e  mov     r9d, [r12+168h]
0x180049a96  shr     r9d, 4
0x180049a9a  and     r9b, r14b; bool
0x180049a9d  mov     r8, rdi; struct WindowsPerformanceRecorder::CControlManager *
0x180049aa0  mov     rdx, [rsp+0D8h+var_90]; struct IProfileCollection *
0x180049aa5  mov     rcx, rax; this
0x180049aa8  call    ?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z; WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)
0x180049aad  mov     edi, eax
0x180049aaf  test    eax, eax
0x180049ab1  jns     short loc_180049B12
0x180049ab3  lea     rax, aComguard; "COMGUARD"
0x180049aba  mov     [rsp+0D8h+Format], rax; Format
0x180049abf  mov     r9d, edi; unsigned int
0x180049ac2  mov     r8d, 165h; char *
0x180049ac8  lea     rdx, aSnapshotondema; "SnapshotOnDemand"
0x180049acf  mov     ecx, 2; this
0x180049ad4  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180049ad9  nop
0x180049ada  test    rbx, rbx
0x180049add  jz      short loc_180049AF0
0x180049adf  mov     rax, [rbx]
0x180049ae2  mov     edx, r14d
0x180049ae5  mov     rcx, rbx
0x180049ae8  mov     rax, [rax]
0x180049aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049af0  mov     [rsp+0D8h+var_80], rsi
0x180049af5  lea     rcx, [rsp+0D8h+var_90]
0x180049afa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180049aff  nop
0x180049b00  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x180049b05  call    cs:__imp_SysFreeString
0x180049b0b  mov     eax, edi
0x180049b0d  jmp     loc_180049C70
0x180049b12  mov     r15, [rbx+8]
0x180049b16  mov     rax, [rbx+10h]
0x180049b1a  mov     [rsp+0D8h+var_78], rax
0x180049b1f  cmp     r15, rax
0x180049b22  jz      loc_180049C0A
0x180049b28  mov     r13, [r15]
0x180049b2b  mov     rdi, [r13+18h]
0x180049b2f  cmp     rdi, [r13+20h]
0x180049b33  jz      short loc_180049BA3
0x180049b35  mov     rax, [rdi]
0x180049b38  sub     rax, qword ptr [rsp+0D8h+var_50.Data1]
0x180049b40  jnz     short loc_180049B4E
0x180049b42  mov     rax, [rdi+8]
0x180049b46  sub     rax, qword ptr [rsp+0D8h+var_50.Data4]
0x180049b4e  test    rax, rax
0x180049b51  jnz     short loc_180049B9A
0x180049b53  mov     rdx, [r12+0B8h]
0x180049b5b  mov     [rsp+0D8h+var_A0], sil; bool
0x180049b60  mov     eax, [rsp+0D8h+var_98]
0x180049b64  mov     [rsp+0D8h+var_A8], eax; unsigned int
0x180049b68  mov     rax, [rsp+0D8h+var_70]
0x180049b6d  mov     [rsp+0D8h+var_B0], rax; char *
0x180049b72  xor     r9d, r9d; unsigned int
0x180049b75  lea     r8, [rsp+0D8h+var_50]; struct _GUID *
0x180049b7d  mov     rdx, [rdx+8]; unsigned __int64
0x180049b81  lea     rcx, [r12-0D0h]; this
0x180049b89  call    ?EnableSnapshotProviderOnSession@CControlManager@WindowsPerformanceRecorder@@AEAAJ_KAEBU_GUID@@KKPEAKK_N@Z; WindowsPerformanceRecorder::CControlManager::EnableSnapshotProviderOnSession(unsigned __int64,_GUID const &,ulong,ulong,ulong *,ulong,bool)
0x180049b8e  mov     r12d, eax
0x180049b91  test    eax, eax
0x180049b93  js      short loc_180049BB1
0x180049b95  mov     r12, [rsp+0D8h+var_68]
0x180049b9a  add     rdi, 108h
0x180049ba1  jmp     short loc_180049B2F
0x180049ba3  add     r15, 8
0x180049ba7  mov     rax, [rsp+0D8h+var_78]
0x180049bac  jmp     loc_180049B1F
0x180049bb1  lea     rax, aComguard; "COMGUARD"
0x180049bb8  mov     [rsp+0D8h+Format], rax; Format
0x180049bbd  mov     r9d, r12d; unsigned int
0x180049bc0  mov     r8d, 177h; char *
0x180049bc6  lea     rdx, aSnapshotondema; "SnapshotOnDemand"
0x180049bcd  mov     ecx, 2; this
0x180049bd2  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180049bd7  nop
0x180049bd8  test    rbx, rbx
0x180049bdb  jz      short loc_180049BEF
0x180049bdd  mov     rax, [rbx]
0x180049be0  mov     edx, r14d
0x180049be3  mov     rcx, rbx
0x180049be6  mov     rax, [rax]
0x180049be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bee  nop
0x180049bef  lea     rcx, [rsp+0D8h+var_90]
0x180049bf4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180049bf9  nop
0x180049bfa  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x180049bff  call    cs:__imp_SysFreeString
0x180049c05  mov     eax, r12d
0x180049c08  jmp     short loc_180049C70
0x180049c0a  test    rbx, rbx
0x180049c0d  jz      short loc_180049C21
0x180049c0f  mov     rax, [rbx]
0x180049c12  mov     edx, r14d
0x180049c15  mov     rcx, rbx
0x180049c18  mov     rax, [rax]
0x180049c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c20  nop
0x180049c21  lea     rcx, [rsp+0D8h+var_90]
0x180049c26  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180049c2b  nop
0x180049c2c  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x180049c31  call    cs:__imp_SysFreeString
0x180049c37  xor     eax, eax
0x180049c39  jmp     short loc_180049C70
0x180049c3b  mov     rcx, [rsp+0D8h+var_80]
0x180049c40  test    rcx, rcx
0x180049c43  jz      short loc_180049C56
0x180049c45  mov     rax, [rcx]
0x180049c48  mov     edx, 1
0x180049c4d  mov     rax, [rax]
0x180049c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c55  nop
0x180049c56  lea     rcx, [rsp+0D8h+var_90]
0x180049c5b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180049c60  nop
0x180049c61  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x180049c66  call    cs:__imp_SysFreeString
0x180049c6c  mov     eax, [rsp+0D8h+var_98]
0x180049c70  mov     rcx, [rsp+0D8h+var_40]
0x180049c78  xor     rcx, rsp; StackCookie
0x180049c7b  call    __security_check_cookie
0x180049c80  add     rsp, 0A0h
0x180049c87  pop     r15
0x180049c89  pop     r14
0x180049c8b  pop     r13
0x180049c8d  pop     r12
0x180049c8f  pop     rdi
0x180049c90  pop     rsi
0x180049c91  pop     rbx
0x180049c92  retn
```
