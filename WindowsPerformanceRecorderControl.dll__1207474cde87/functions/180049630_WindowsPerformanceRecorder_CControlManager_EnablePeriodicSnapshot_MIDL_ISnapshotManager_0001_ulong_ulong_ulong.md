# WindowsPerformanceRecorder::CControlManager::EnablePeriodicSnapshot(__MIDL_ISnapshotManager_0001,ulong,ulong *,ulong)

- ea: `0x180049630`
- end: `0x180049962`
- name: `?EnablePeriodicSnapshot@CControlManager@WindowsPerformanceRecorder@@UEAAJW4__MIDL_ISnapshotManager_0001@@KPEAKK@Z`
- size: `818`
- prototype: `int __high(enum __MIDL_ISnapshotManager_0001, unsigned int, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18001a92c`
- `0x18001c8bc`
- `0x18001e6e0`
- `0x1800248d8`
- `0x180040a04`
- `0x180049630`
- `0x18004ece0`
- `0x18004ed10`
- `0x18006264c`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180049725`
- `OLEAUT32!__imp_SysFreeString` at `0x1800497d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800498cf`
- `OLEAUT32!__imp_SysFreeString` at `0x180049900`
- `OLEAUT32!__imp_SysFreeString` at `0x180049935`
- `OLEAUT32!__imp_SysFreeString` at `0x180049725`
- `OLEAUT32!__imp_SysFreeString` at `0x1800497d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800498cf`
- `OLEAUT32!__imp_SysFreeString` at `0x180049900`
- `OLEAUT32!__imp_SysFreeString` at `0x180049935`

## string_xrefs

- `0x1800496df`: `COMGUARD`
- `0x18004977f`: `COMGUARD`
- `0x180049882`: `COMGUARD`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::EnablePeriodicSnapshot(
        __int64 a1,
        int a2,
        unsigned int a3,
        char *a4,
        unsigned int a5)
{
  unsigned int v6; // ebx
  unsigned int v7; // r15d
  struct WindowsPerformanceRecorder::CControlManager *v8; // rdi
  signed int v9; // eax
  _QWORD *v11; // rbx
  signed int v12; // eax
  unsigned int v13; // edi
  WindowsPerformanceRecorder::CETWProperties *v14; // r14
  WindowsPerformanceRecorder::CETWProperties *v15; // rax
  __int64 v16; // r13
  _QWORD *i; // rdi
  __int64 v18; // rax
  signed int v19; // r15d
  unsigned int Format; // [rsp+20h] [rbp-B8h]
  char *v21; // [rsp+28h] [rbp-B0h]
  char *v22; // [rsp+28h] [rbp-B0h]
  unsigned int v24; // [rsp+40h] [rbp-98h]
  struct IProfileCollection *v25; // [rsp+48h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-88h] BYREF
  void (__fastcall ***v27)(_QWORD, __int64); // [rsp+58h] [rbp-80h]
  WindowsPerformanceRecorder::CETWProperties *v28; // [rsp+60h] [rbp-78h]
  char *v29; // [rsp+68h] [rbp-70h]
  __int64 v30; // [rsp+70h] [rbp-68h]
  ATL::CAtlException *v31; // [rsp+78h] [rbp-60h] BYREF
  struct _GUID v32; // [rsp+80h] [rbp-58h] BYREF

  v30 = -2;
  v29 = a4;
  bstrString = 0;
  v25 = 0;
  if ( a2 != 1 )
  {
    v6 = -2147024809;
LABEL_9:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    SysFreeString(bstrString);
    return v6;
  }
  v32 = (struct _GUID)HeapSnapGuid;
  v7 = a5;
  if ( a5 > 8 )
  {
    v6 = -984068077;
    goto LABEL_9;
  }
  v8 = (struct WindowsPerformanceRecorder::CControlManager *)(a1 - 208);
  v9 = WindowsPerformanceRecorder::CControlManager::QueryRunningProfile(
         (WindowsPerformanceRecorder::CControlManager *)(a1 - 208),
         1,
         &bstrString,
         0,
         &v25);
  v6 = v9;
  if ( v9 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "EnablePeriodicSnapshot",
      (const char *)0x19B,
      v9,
      "COMGUARD",
      v21);
    goto LABEL_9;
  }
  if ( (*(_BYTE *)(a1 + 360) & 2) != 0 )
  {
    v6 = -984076288;
    goto LABEL_9;
  }
  try
  {
    v27 = 0;
    v28 = (WindowsPerformanceRecorder::CETWProperties *)operator new(0x1A8u);
    v11 = (_QWORD *)WindowsPerformanceRecorder::CETWProperties::CETWProperties(v28);
    v27 = (void (__fastcall ***)(_QWORD, __int64))v11;
    v12 = WindowsPerformanceRecorder::CETWProperties::Initialize(
            (WindowsPerformanceRecorder::CETWProperties *)v11,
            v25,
            v8,
            (*(_DWORD *)(a1 + 360) & 0x10) != 0);
  }
  catch ( ATL::CAtlException *v31 )
  {
    v24 = *(_DWORD *)v31;
    if ( v27 )
      (**v27)(v27, 1);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    SysFreeString(bstrString);
    return v24;
  }
  v13 = v12;
  if ( v12 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "EnablePeriodicSnapshot",
      (const char *)0x1A6,
      v12,
      "COMGUARD",
      v21);
    if ( v11 )
      (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
    v27 = 0;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    SysFreeString(bstrString);
    return v13;
  }
  v14 = (WindowsPerformanceRecorder::CETWProperties *)v11[1];
  v15 = (WindowsPerformanceRecorder::CETWProperties *)v11[2];
  v28 = v15;
LABEL_15:
  if ( v14 != v15 )
  {
    v16 = *(_QWORD *)v14;
    for ( i = *(_QWORD **)(*(_QWORD *)v14 + 24LL); ; i += 33 )
    {
      if ( i == *(_QWORD **)(v16 + 32) )
      {
        v14 = (WindowsPerformanceRecorder::CETWProperties *)((char *)v14 + 8);
        v15 = v28;
        goto LABEL_15;
      }
      v18 = *i - *(_QWORD *)&v32.Data1;
      if ( *i == *(_QWORD *)&v32.Data1 )
        v18 = i[1] - *(_QWORD *)v32.Data4;
      if ( !v18 )
      {
        v19 = WindowsPerformanceRecorder::CControlManager::EnableSnapshotProviderOnSession(
                (WindowsPerformanceRecorder::CControlManager *)(a1 - 208),
                *(_QWORD *)(*(_QWORD *)(a1 + 184) + 8LL),
                &v32,
                a3,
                Format,
                (unsigned int *)v29,
                v7,
                1);
        if ( v19 < 0 )
        {
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            "EnablePeriodicSnapshot",
            (const char *)0x1B8,
            v19,
            "COMGUARD",
            v22);
          if ( v11 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
          SysFreeString(bstrString);
          return (unsigned int)v19;
        }
        v7 = a5;
      }
    }
  }
  if ( v11 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  SysFreeString(bstrString);
  return 0;
}

```

## disassembly

```asm
0x180049630  push    rbx
0x180049632  push    rsi
0x180049633  push    rdi
0x180049634  push    r12
0x180049636  push    r13
0x180049638  push    r14
0x18004963a  push    r15
0x18004963c  sub     rsp, 0A0h
0x180049643  mov     [rsp+0D8h+var_68], 0FFFFFFFFFFFFFFFEh
0x18004964c  mov     rax, cs:__security_cookie
0x180049653  xor     rax, rsp
0x180049656  mov     [rsp+0D8h+var_48], rax
0x18004965e  mov     [rsp+0D8h+var_70], r9
0x180049663  mov     [rsp+0D8h+var_98], r8d
0x180049668  mov     r12, rcx
0x18004966b  mov     [rsp+0D8h+bstrString], 0
0x180049674  mov     [rsp+0D8h+var_90], 0
0x18004967d  cmp     edx, 1
0x180049680  jz      short loc_18004968C
0x180049682  mov     ebx, 80070057h
0x180049687  jmp     loc_180049715
0x18004968c  movups  xmm0, cs:HeapSnapGuid
0x180049693  movdqu  xmmword ptr [rsp+0D8h+var_58.Data1], xmm0
0x18004969c  mov     r15d, [rsp+0D8h+arg_20]
0x1800496a4  cmp     r15d, 8
0x1800496a8  jbe     short loc_1800496B1
0x1800496aa  mov     ebx, 0C5585013h
0x1800496af  jmp     short loc_180049715
0x1800496b1  lea     rdi, [rcx-0D0h]
0x1800496b8  lea     rax, [rsp+0D8h+var_90]
0x1800496bd  mov     [rsp+0D8h+Format], rax; unsigned int
0x1800496c2  xor     r9d, r9d; unsigned __int16 **
0x1800496c5  lea     r8, [rsp+0D8h+bstrString]; unsigned __int16 **
0x1800496ca  lea     esi, [r9+1]
0x1800496ce  mov     dl, sil; bool
0x1800496d1  mov     rcx, rdi; this
0x1800496d4  call    ?QueryRunningProfile@CControlManager@WindowsPerformanceRecorder@@AEAAJ_NPEAPEAG1PEAPEAUIProfileCollection@@@Z; WindowsPerformanceRecorder::CControlManager::QueryRunningProfile(bool,ushort * *,ushort * *,IProfileCollection * *)
0x1800496d9  mov     ebx, eax
0x1800496db  test    eax, eax
0x1800496dd  jns     short loc_180049705
0x1800496df  lea     rax, aComguard; "COMGUARD"
0x1800496e6  mov     [rsp+0D8h+Format], rax; Format
0x1800496eb  mov     r9d, ebx; unsigned int
0x1800496ee  mov     r8d, 19Bh; char *
0x1800496f4  lea     rdx, aEnableperiodic; "EnablePeriodicSnapshot"
0x1800496fb  lea     ecx, [rsi+1]; this
0x1800496fe  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180049703  jmp     short loc_180049715
0x180049705  test    byte ptr [r12+168h], 2
0x18004970e  jz      short loc_180049732
0x180049710  mov     ebx, 0C5583000h
0x180049715  lea     rcx, [rsp+0D8h+var_90]
0x18004971a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004971f  nop
0x180049720  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x180049725  call    cs:__imp_SysFreeString
0x18004972b  mov     eax, ebx
0x18004972d  jmp     loc_18004993F
0x180049732  mov     [rsp+0D8h+var_80], 0
0x18004973b  mov     ecx, 1A8h; Size
0x180049740  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049745  mov     [rsp+0D8h+var_78], rax
0x18004974a  mov     rcx, rax; this
0x18004974d  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x180049752  mov     rbx, rax
0x180049755  mov     [rsp+0D8h+var_80], rax
0x18004975a  mov     r9d, [r12+168h]
0x180049762  shr     r9d, 4
0x180049766  and     r9b, sil; bool
0x180049769  mov     r8, rdi; struct WindowsPerformanceRecorder::CControlManager *
0x18004976c  mov     rdx, [rsp+0D8h+var_90]; struct IProfileCollection *
0x180049771  mov     rcx, rax; this
0x180049774  call    ?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z; WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)
0x180049779  mov     edi, eax
0x18004977b  test    eax, eax
0x18004977d  jns     short loc_1800497E1
0x18004977f  lea     rax, aComguard; "COMGUARD"
0x180049786  mov     [rsp+0D8h+Format], rax; Format
0x18004978b  mov     r9d, edi; unsigned int
0x18004978e  mov     r8d, 1A6h; char *
0x180049794  lea     rdx, aEnableperiodic; "EnablePeriodicSnapshot"
0x18004979b  mov     ecx, 2; this
0x1800497a0  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x1800497a5  nop
0x1800497a6  test    rbx, rbx
0x1800497a9  jz      short loc_1800497BB
0x1800497ab  mov     rax, [rbx]
0x1800497ae  mov     edx, esi
0x1800497b0  mov     rcx, rbx
0x1800497b3  mov     rax, [rax]
0x1800497b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497bb  mov     [rsp+0D8h+var_80], 0
0x1800497c4  lea     rcx, [rsp+0D8h+var_90]
0x1800497c9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800497ce  nop
0x1800497cf  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x1800497d4  call    cs:__imp_SysFreeString
0x1800497da  mov     eax, edi
0x1800497dc  jmp     loc_18004993F
0x1800497e1  mov     r14, [rbx+8]
0x1800497e5  mov     rax, [rbx+10h]
0x1800497e9  mov     [rsp+0D8h+var_78], rax
0x1800497ee  cmp     r14, rax
0x1800497f1  jz      loc_1800498DA
0x1800497f7  mov     r13, [r14]
0x1800497fa  mov     rdi, [r13+18h]
0x1800497fe  cmp     rdi, [r13+20h]
0x180049802  jz      short loc_180049874
0x180049804  mov     rax, [rdi]
0x180049807  sub     rax, qword ptr [rsp+0D8h+var_58.Data1]
0x18004980f  jnz     short loc_18004981D
0x180049811  mov     rax, [rdi+8]
0x180049815  sub     rax, qword ptr [rsp+0D8h+var_58.Data4]
0x18004981d  test    rax, rax
0x180049820  jnz     short loc_18004986B
0x180049822  mov     rdx, [r12+0B8h]
0x18004982a  mov     [rsp+0D8h+var_A0], sil; bool
0x18004982f  mov     [rsp+0D8h+var_A8], r15d; unsigned int
0x180049834  mov     rax, [rsp+0D8h+var_70]
0x180049839  mov     [rsp+0D8h+var_B0], rax; char *
0x18004983e  mov     r9d, [rsp+0D8h+var_98]; unsigned int
0x180049843  lea     r8, [rsp+0D8h+var_58]; struct _GUID *
0x18004984b  mov     rdx, [rdx+8]; unsigned __int64
0x18004984f  lea     rcx, [r12-0D0h]; this
0x180049857  call    ?EnableSnapshotProviderOnSession@CControlManager@WindowsPerformanceRecorder@@AEAAJ_KAEBU_GUID@@KKPEAKK_N@Z; WindowsPerformanceRecorder::CControlManager::EnableSnapshotProviderOnSession(unsigned __int64,_GUID const &,ulong,ulong,ulong *,ulong,bool)
0x18004985c  mov     r15d, eax
0x18004985f  test    eax, eax
0x180049861  js      short loc_180049882
0x180049863  mov     r15d, [rsp+0D8h+arg_20]
0x18004986b  add     rdi, 108h
0x180049872  jmp     short loc_1800497FE
0x180049874  add     r14, 8
0x180049878  mov     rax, [rsp+0D8h+var_78]
0x18004987d  jmp     loc_1800497EE
0x180049882  lea     rax, aComguard; "COMGUARD"
0x180049889  mov     [rsp+0D8h+Format], rax; Format
0x18004988e  mov     r9d, r15d; unsigned int
0x180049891  mov     r8d, 1B8h; char *
0x180049897  lea     rdx, aEnableperiodic; "EnablePeriodicSnapshot"
0x18004989e  mov     ecx, 2; this
0x1800498a3  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x1800498a8  nop
0x1800498a9  test    rbx, rbx
0x1800498ac  jz      short loc_1800498BF
0x1800498ae  mov     rax, [rbx]
0x1800498b1  mov     edx, esi
0x1800498b3  mov     rcx, rbx
0x1800498b6  mov     rax, [rax]
0x1800498b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498be  nop
0x1800498bf  lea     rcx, [rsp+0D8h+var_90]
0x1800498c4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800498c9  nop
0x1800498ca  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x1800498cf  call    cs:__imp_SysFreeString
0x1800498d5  mov     eax, r15d
0x1800498d8  jmp     short loc_18004993F
0x1800498da  test    rbx, rbx
0x1800498dd  jz      short loc_1800498F0
0x1800498df  mov     rax, [rbx]
0x1800498e2  mov     edx, esi
0x1800498e4  mov     rcx, rbx
0x1800498e7  mov     rax, [rax]
0x1800498ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498ef  nop
0x1800498f0  lea     rcx, [rsp+0D8h+var_90]
0x1800498f5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800498fa  nop
0x1800498fb  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x180049900  call    cs:__imp_SysFreeString
0x180049906  xor     eax, eax
0x180049908  jmp     short loc_18004993F
0x18004990a  mov     rcx, [rsp+0D8h+var_80]
0x18004990f  test    rcx, rcx
0x180049912  jz      short loc_180049925
0x180049914  mov     rax, [rcx]
0x180049917  mov     edx, 1
0x18004991c  mov     rax, [rax]
0x18004991f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049924  nop
0x180049925  lea     rcx, [rsp+0D8h+var_90]
0x18004992a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004992f  nop
0x180049930  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x180049935  call    cs:__imp_SysFreeString
0x18004993b  mov     eax, [rsp+0D8h+var_98]
0x18004993f  mov     rcx, [rsp+0D8h+var_48]
0x180049947  xor     rcx, rsp; StackCookie
0x18004994a  call    __security_check_cookie
0x18004994f  add     rsp, 0A0h
0x180049956  pop     r15
0x180049958  pop     r14
0x18004995a  pop     r13
0x18004995c  pop     r12
0x18004995e  pop     rdi
0x18004995f  pop     rsi
0x180049960  pop     rbx
0x180049961  retn
```
