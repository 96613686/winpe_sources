# CWMIBroker::VerifyByTemplate(IWbemServices *,IWbemClassObject * *,ushort *,int &)

- ea: `0x140004620`
- end: `0x140004bb9`
- name: `?VerifyByTemplate@CWMIBroker@@AEAAJPEAUIWbemServices@@PEAPEAUIWbemClassObject@@PEAGAEAH@Z`
- size: `1433`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct IWbemServices *, struct IWbemClassObject **, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400037f0`

## callees

- `0x140002b5c`
- `0x140002de4`
- `0x140002e14`
- `0x140002ee4`
- `0x140004620`
- `0x140017010`

## import_xrefs

- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x1400047e6`
- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x140004980`
- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x140004ae3`
- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x1400047e6`
- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x140004980`
- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x140004ae3`
- `OLEAUT32!__imp_SysAllocString` at `0x14000465d`
- `OLEAUT32!__imp_SysAllocString` at `0x14000465d`

## pseudocode

```c
__int64 __fastcall CWMIBroker::VerifyByTemplate(
        const unsigned __int16 **this,
        struct IWbemServices *a2,
        struct IWbemClassObject **a3,
        unsigned __int16 *a4,
        int *a5)
{
  struct IWbemClassObject **v5; // r14
  struct IWbemServices *v6; // rsi
  OLECHAR *v7; // rax
  OLECHAR *v8; // r15
  int v10; // eax
  struct IWbemClassObject *v11; // rbx
  int v12; // edi
  struct IWbemClassObject *v13; // rcx
  struct CInsertionString *v14; // r13
  struct CInsertionString *v15; // r12
  struct CInsertionString *v16; // r15
  struct CInsertionString *v17; // r14
  struct CInsertionString *v18; // rsi
  const struct CInsertionString *v19; // rdi
  const struct CInsertionString *v20; // rax
  int v21; // ecx
  int v22; // edi
  struct CInsertionString *v23; // r13
  struct CInsertionString *v24; // r12
  struct CInsertionString *v25; // r15
  struct CInsertionString *v26; // r14
  struct CInsertionString *v27; // rsi
  const struct CInsertionString *v28; // rdi
  const struct CInsertionString *v29; // rax
  struct CInsertionString *v30; // r13
  struct CInsertionString *v31; // r12
  struct CInsertionString *v32; // r15
  struct CInsertionString *v33; // r14
  struct CInsertionString *v34; // rsi
  const struct CInsertionString *v35; // rdi
  const struct CInsertionString *v36; // rax
  int v37; // [rsp+68h] [rbp-A0h]
  int v38; // [rsp+68h] [rbp-A0h]
  struct CInsertionString *v39; // [rsp+70h] [rbp-98h]
  struct CInsertionString *v40; // [rsp+70h] [rbp-98h]
  struct CInsertionString *v41; // [rsp+70h] [rbp-98h]
  struct CInsertionString *v42; // [rsp+78h] [rbp-90h]
  struct CInsertionString *v43; // [rsp+78h] [rbp-90h]
  struct CInsertionString *v44; // [rsp+78h] [rbp-90h]
  OLECHAR *v45; // [rsp+80h] [rbp-88h]
  struct CInsertionString *v46; // [rsp+80h] [rbp-88h]
  struct CInsertionString *v47; // [rsp+80h] [rbp-88h]
  struct IWbemClassObject *v48; // [rsp+88h] [rbp-80h] BYREF
  struct IWbemClassObject *v49; // [rsp+90h] [rbp-78h] BYREF
  _BYTE *v50; // [rsp+98h] [rbp-70h]
  _BYTE *v51; // [rsp+A0h] [rbp-68h]
  _BYTE *v52; // [rsp+A8h] [rbp-60h]
  _BYTE *v53; // [rsp+B0h] [rbp-58h]
  _BYTE *v54; // [rsp+B8h] [rbp-50h]
  _BYTE *v55; // [rsp+C0h] [rbp-48h]
  _BYTE *v56; // [rsp+C8h] [rbp-40h]
  _BYTE *v57; // [rsp+D0h] [rbp-38h]
  _BYTE *v58; // [rsp+D8h] [rbp-30h]
  _BYTE *v59; // [rsp+E0h] [rbp-28h]
  _BYTE v60[16]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v61[16]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v62[16]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v63[16]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v64[16]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v65[16]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v66[16]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v67[16]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v68[16]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v69[16]; // [rsp+178h] [rbp+70h] BYREF
  struct CInsertionString *v70; // [rsp+188h] [rbp+80h]
  struct IWbemClassObject *v71; // [rsp+190h] [rbp+88h]
  OLECHAR *v72; // [rsp+198h] [rbp+90h] BYREF

  v5 = a3;
  v6 = a2;
  v49 = 0;
  v7 = SysAllocString(a4);
  v8 = v7;
  v45 = v7;
  if ( !v7 )
    return 2147749894LL;
  v72 = v7;
  v10 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, _QWORD, _QWORD, struct IWbemClassObject **, _QWORD))v6->lpVtbl->GetObjectA)(
          v6,
          v7,
          0,
          0,
          &v49,
          0);
  v11 = v49;
  v71 = v49;
  if ( v10 < 0 || !v49 )
  {
    v22 = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, _QWORD, _QWORD, _QWORD))v6->lpVtbl->PutClass)(
            v6,
            *v5,
            0,
            0,
            0);
    v38 = v22;
    if ( v22 < 0 )
    {
      v59 = v69;
      v46 = CInsertionString::CInsertionString((CInsertionString *)v69);
      v58 = v68;
      v43 = CInsertionString::CInsertionString((CInsertionString *)v68);
      v57 = v67;
      v40 = CInsertionString::CInsertionString((CInsertionString *)v67);
      v56 = v66;
      v23 = CInsertionString::CInsertionString((CInsertionString *)v66);
      v55 = v65;
      v24 = CInsertionString::CInsertionString((CInsertionString *)v65);
      v54 = v64;
      v25 = CInsertionString::CInsertionString((CInsertionString *)v64);
      v53 = v63;
      v26 = CInsertionString::CInsertionString((CInsertionString *)v63);
      v52 = v62;
      v27 = (struct CInsertionString *)CInsertionString::CInsertionString(v62, (unsigned int)v22);
      v51 = v61;
      v28 = CInsertionString::CInsertionString((CInsertionString *)v61, this[1]);
      v50 = v60;
      v29 = CInsertionString::CInsertionString((CInsertionString *)v60, L"Win32_PerfRawData");
      CAdapUtility::NTLogEvent(
        (__int64)v40,
        (__int64)WBEM_MC_ADAP_PERFLIB_PUTCLASS_FAILURE,
        v29,
        v28,
        v27,
        v26,
        v25,
        v24,
        v23,
        v40,
        v43,
        v46);
      goto LABEL_19;
    }
    *a5 = 1;
LABEL_16:
    v48 = 0;
    v12 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, _QWORD, _QWORD, struct IWbemClassObject **, _QWORD))v6->lpVtbl->GetObjectA)(
            v6,
            v8,
            0,
            0,
            &v48,
            0);
    v38 = v12;
    if ( v12 >= 0 )
    {
      ((void (__fastcall *)(struct IWbemClassObject *))(*v5)->lpVtbl->Release)(*v5);
      *v5 = v48;
      goto LABEL_20;
    }
    v59 = v69;
    v47 = CInsertionString::CInsertionString((CInsertionString *)v69);
    v58 = v68;
    v44 = CInsertionString::CInsertionString((CInsertionString *)v68);
    v57 = v67;
    v41 = CInsertionString::CInsertionString((CInsertionString *)v67);
    v56 = v66;
    v30 = CInsertionString::CInsertionString((CInsertionString *)v66);
    v55 = v65;
    v31 = CInsertionString::CInsertionString((CInsertionString *)v65);
    v54 = v64;
    v32 = CInsertionString::CInsertionString((CInsertionString *)v64);
    v53 = v63;
    v33 = CInsertionString::CInsertionString((CInsertionString *)v63);
    v52 = v62;
    v34 = (struct CInsertionString *)CInsertionString::CInsertionString(v62, (unsigned int)v12);
    v51 = v61;
    v35 = CInsertionString::CInsertionString((CInsertionString *)v61, this[1]);
    v50 = v60;
    v36 = CInsertionString::CInsertionString((CInsertionString *)v60, L"Win32_PerfRawData");
    CAdapUtility::NTLogEvent(
      (__int64)v41,
      (__int64)WBEM_MC_ADAP_PERFLIB_PUTCLASS_FAILURE,
      v36,
      v35,
      v34,
      v33,
      v32,
      v31,
      v30,
      v41,
      v44,
      v47);
LABEL_19:
    v12 = v38;
    goto LABEL_20;
  }
  if ( ((unsigned int (__fastcall *)(struct IWbemClassObject *, __int64, struct IWbemClassObject *))v49->lpVtbl->CompareTo)(
         v49,
         2,
         *v5) )
  {
    v12 = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, __int64))v6->lpVtbl->PutClass)(
            v6,
            *v5,
            64);
    v37 = v12;
    if ( v12 >= 0 )
    {
      v21 = 1;
      *a5 = 1;
    }
    else
    {
      LODWORD(v48) = 0;
      v50 = v60;
      v70 = CInsertionString::CInsertionString((CInsertionString *)v60);
      v51 = v61;
      v39 = CInsertionString::CInsertionString((CInsertionString *)v61);
      v52 = v62;
      v42 = CInsertionString::CInsertionString((CInsertionString *)v62);
      v53 = v63;
      v14 = CInsertionString::CInsertionString((CInsertionString *)v63);
      v54 = v64;
      v15 = CInsertionString::CInsertionString((CInsertionString *)v64);
      v55 = v65;
      v16 = CInsertionString::CInsertionString((CInsertionString *)v65);
      v56 = v66;
      v17 = CInsertionString::CInsertionString((CInsertionString *)v66);
      v57 = v67;
      v18 = (struct CInsertionString *)CInsertionString::CInsertionString(v67, (unsigned int)v12);
      v58 = v68;
      v19 = CInsertionString::CInsertionString((CInsertionString *)v68, this[1]);
      v59 = v69;
      v20 = CInsertionString::CInsertionString((CInsertionString *)v69, L"Win32_PerfRawData");
      CAdapUtility::NTLogEvent(
        (__int64)v42,
        (__int64)WBEM_MC_ADAP_PERFLIB_PUTCLASS_FAILURE,
        v20,
        v19,
        v18,
        v17,
        v16,
        v15,
        v14,
        v42,
        v39,
        v70);
      v12 = v37;
      v6 = a2;
      v5 = a3;
      v21 = 0;
      v8 = v45;
    }
    if ( v12 < 0 || !v21 )
      goto LABEL_20;
    goto LABEL_16;
  }
  v12 = 0;
  ((void (__fastcall *)(struct IWbemClassObject *))(*v5)->lpVtbl->Release)(*v5);
  v13 = v49;
  *v5 = v49;
  ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->AddRef)(v13);
LABEL_20:
  if ( v11 )
    ((void (__fastcall *)(struct IWbemClassObject *))v11->lpVtbl->Release)(v11);
  v71 = 0;
  CSysFreeMe::~CSysFreeMe(&v72);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140004620  mov     rax, rsp
0x140004623  mov     [rax+20h], rbx
0x140004627  mov     [rax+18h], r8
0x14000462b  mov     [rax+10h], rdx
0x14000462f  mov     [rax+8], rcx
0x140004633  push    rbp
0x140004634  push    rsi
0x140004635  push    rdi
0x140004636  push    r12
0x140004638  push    r13
0x14000463a  push    r14
0x14000463c  push    r15
0x14000463e  lea     rbp, [rax-0D8h]
0x140004645  sub     rsp, 1A0h
0x14000464c  mov     r14, r8
0x14000464f  mov     rsi, rdx
0x140004652  mov     [rbp+0D0h+var_148], 0
0x14000465a  mov     rcx, r9; psz
0x14000465d  call    cs:__imp_SysAllocString
0x140004663  mov     r15, rax
0x140004666  mov     [rsp+78h], rax
0x14000466b  test    rax, rax
0x14000466e  jnz     short loc_14000467A
0x140004670  mov     eax, 80041006h
0x140004675  jmp     loc_140004B9E
0x14000467a  mov     [rbp+0D0h+var_40], r15
0x140004681  mov     rax, [rsi]
0x140004684  mov     [rsp+1D0h+var_1A8], 0
0x14000468d  lea     rcx, [rbp+0D0h+var_148]
0x140004691  mov     [rsp+1D0h+var_1B0], rcx
0x140004696  xor     r9d, r9d
0x140004699  xor     r8d, r8d
0x14000469c  mov     rdx, r15
0x14000469f  mov     rcx, rsi
0x1400046a2  mov     rax, [rax+30h]
0x1400046a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046ab  mov     rbx, [rbp+0D0h+var_148]
0x1400046af  mov     [rbp+0D0h+var_48], rbx
0x1400046b6  test    eax, eax
0x1400046b8  js      loc_1400048B1
0x1400046be  mov     rcx, [rbp+0D0h+var_148]
0x1400046c2  test    rcx, rcx
0x1400046c5  jz      loc_1400048B1
0x1400046cb  mov     rax, [rcx]
0x1400046ce  mov     r8, [r14]
0x1400046d1  mov     edx, 2
0x1400046d6  mov     rax, [rax+80h]
0x1400046dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046e2  test    eax, eax
0x1400046e4  jnz     short loc_14000470F
0x1400046e6  xor     edi, edi
0x1400046e8  mov     rcx, [r14]
0x1400046eb  mov     rax, [rcx]
0x1400046ee  mov     rax, [rax+10h]
0x1400046f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046f7  mov     rcx, [rbp+0D0h+var_148]
0x1400046fb  mov     [r14], rcx
0x1400046fe  mov     rax, [rcx]
0x140004701  mov     rax, [rax+8]
0x140004705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000470a  jmp     loc_140004B71
0x14000470f  mov     rax, [rsi]
0x140004712  mov     [rsp+1D0h+var_1B0], 0
0x14000471b  xor     r9d, r9d
0x14000471e  lea     r8d, [r9+40h]
0x140004722  mov     rdx, [r14]
0x140004725  mov     rcx, rsi
0x140004728  mov     rax, [rax+40h]
0x14000472c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004731  mov     edi, eax
0x140004733  mov     dword ptr [rsp+1D0h+var_170], eax
0x140004737  test    eax, eax
0x140004739  jns     loc_14000488E
0x14000473f  xor     ecx, ecx
0x140004741  mov     dword ptr [rbp+0D0h+var_150], ecx
0x140004744  lea     rax, [rbp+0D0h+var_F0]
0x140004748  mov     [rbp+0D0h+var_140], rax
0x14000474c  lea     rcx, [rbp+0D0h+var_F0]; this
0x140004750  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140004755  mov     [rbp+0D0h+var_50], rax
0x14000475c  lea     rax, [rbp+0D0h+var_E0]
0x140004760  mov     [rbp+0D0h+var_138], rax
0x140004764  lea     rcx, [rbp+0D0h+var_E0]; this
0x140004768  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x14000476d  mov     [rsp+1D0h+var_168], rax
0x140004772  lea     rax, [rbp+0D0h+var_D0]
0x140004776  mov     [rbp+0D0h+var_130], rax
0x14000477a  lea     rcx, [rbp+0D0h+var_D0]; this
0x14000477e  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140004783  mov     [rsp+1D0h+var_160], rax
0x140004788  lea     rax, [rbp+0D0h+var_C0]
0x14000478c  mov     [rbp+0D0h+var_128], rax
0x140004790  lea     rcx, [rbp+0D0h+var_C0]; this
0x140004794  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140004799  mov     r13, rax
0x14000479c  lea     rax, [rbp+0D0h+var_B0]
0x1400047a0  mov     [rbp+0D0h+var_120], rax
0x1400047a4  lea     rcx, [rbp+0D0h+var_B0]; this
0x1400047a8  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1400047ad  mov     r12, rax
0x1400047b0  lea     rax, [rbp+0D0h+var_A0]
0x1400047b4  mov     [rbp+0D0h+var_118], rax
0x1400047b8  lea     rcx, [rbp+0D0h+var_A0]; this
0x1400047bc  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1400047c1  mov     r15, rax
0x1400047c4  lea     rax, [rbp+0D0h+var_90]
0x1400047c8  mov     [rbp+0D0h+var_110], rax
0x1400047cc  lea     rcx, [rbp+0D0h+var_90]; this
0x1400047d0  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1400047d5  mov     r14, rax
0x1400047d8  lea     rax, [rbp+0D0h+var_80]
0x1400047dc  mov     [rbp+0D0h+var_108], rax
0x1400047e0  mov     edx, edi
0x1400047e2  lea     rcx, [rbp+0D0h+var_80]
0x1400047e6  call    cs:__imp_??0CInsertionString@@QEAA@VCHex@@@Z; CInsertionString::CInsertionString(CHex)
0x1400047ec  mov     rsi, rax
0x1400047ef  lea     rax, [rbp+0D0h+var_70]
0x1400047f3  mov     [rbp+0D0h+var_100], rax
0x1400047f7  mov     rdx, [rbp+0D0h+arg_0]
0x1400047fe  mov     rdx, [rdx+8]; unsigned __int16 *
0x140004802  lea     rcx, [rbp+0D0h+var_70]; this
0x140004806  call    ??0CInsertionString@@QEAA@PEBG@Z; CInsertionString::CInsertionString(ushort const *)
0x14000480b  mov     rdi, rax
0x14000480e  lea     rax, [rbp+0D0h+var_60]
0x140004812  mov     [rbp+0D0h+var_F8], rax
0x140004816  lea     rdx, aWin32Perfrawda; "Win32_PerfRawData"
0x14000481d  lea     rcx, [rbp+0D0h+var_60]; this
0x140004821  call    ??0CInsertionString@@QEAA@PEBG@Z; CInsertionString::CInsertionString(ushort const *)
0x140004826  nop
0x140004827  mov     rcx, [rbp+0D0h+var_50]
0x14000482e  mov     qword ptr [rsp+1D0h+var_178], rcx
0x140004833  mov     rcx, [rsp+1D0h+var_168]
0x140004838  mov     [rsp+1D0h+var_180], rcx
0x14000483d  mov     rcx, [rsp+1D0h+var_160]
0x140004842  mov     [rsp+1D0h+var_188], rcx
0x140004847  mov     [rsp+1D0h+var_190], r13
0x14000484c  mov     [rsp+1D0h+var_198], r12
0x140004851  mov     [rsp+1D0h+var_1A0], r15
0x140004856  mov     [rsp+1D0h+var_1A8], r14
0x14000485b  mov     [rsp+1D0h+var_1B0], rsi
0x140004860  mov     r9, rdi
0x140004863  mov     r8, rax
0x140004866  lea     rdx, WBEM_MC_ADAP_PERFLIB_PUTCLASS_FAILURE
0x14000486d  call    ?NTLogEvent@CAdapUtility@@SAJKAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z; CAdapUtility::NTLogEvent(ulong,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)
0x140004872  mov     edi, dword ptr [rsp+1D0h+var_170]
0x140004876  mov     rsi, [rbp+0D0h+arg_8]
0x14000487d  mov     r14, [rbp+0D0h+arg_10]
0x140004884  mov     ecx, dword ptr [rbp+0D0h+var_150]
0x140004887  mov     r15, [rsp+78h]
0x14000488c  jmp     short loc_14000489C
0x14000488e  mov     ecx, 1
0x140004893  mov     rax, [rbp+0D0h+arg_20]
0x14000489a  mov     [rax], ecx
0x14000489c  test    edi, edi
0x14000489e  js      loc_140004B71
0x1400048a4  test    ecx, ecx
0x1400048a6  jnz     loc_1400049EC
0x1400048ac  jmp     loc_140004B71
0x1400048b1  mov     rax, [rsi]
0x1400048b4  mov     [rsp+1D0h+var_1B0], 0
0x1400048bd  xor     r9d, r9d
0x1400048c0  xor     r8d, r8d
0x1400048c3  mov     rdx, [r14]
0x1400048c6  mov     rcx, rsi
0x1400048c9  mov     rax, [rax+40h]
0x1400048cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048d2  mov     edi, eax
0x1400048d4  mov     dword ptr [rsp+1D0h+var_170], eax
0x1400048d8  test    eax, eax
0x1400048da  jns     loc_1400049DF
0x1400048e0  lea     rax, [rbp+0D0h+var_60]
0x1400048e4  mov     [rbp+0D0h+var_F8], rax
0x1400048e8  lea     rcx, [rbp+0D0h+var_60]; this
0x1400048ec  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1400048f1  mov     [rsp+78h], rax
0x1400048f6  lea     rax, [rbp+0D0h+var_70]
0x1400048fa  mov     [rbp+0D0h+var_100], rax
0x1400048fe  lea     rcx, [rbp+0D0h+var_70]; this
0x140004902  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140004907  mov     [rsp+1D0h+var_160], rax
0x14000490c  lea     rax, [rbp+0D0h+var_80]
0x140004910  mov     [rbp+0D0h+var_108], rax
0x140004914  lea     rcx, [rbp+0D0h+var_80]; this
0x140004918  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x14000491d  mov     [rsp+1D0h+var_168], rax
0x140004922  lea     rax, [rbp+0D0h+var_90]
0x140004926  mov     [rbp+0D0h+var_110], rax
0x14000492a  lea     rcx, [rbp+0D0h+var_90]; this
0x14000492e  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140004933  mov     r13, rax
0x140004936  lea     rax, [rbp+0D0h+var_A0]
0x14000493a  mov     [rbp+0D0h+var_118], rax
0x14000493e  lea     rcx, [rbp+0D0h+var_A0]; this
0x140004942  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140004947  mov     r12, rax
0x14000494a  lea     rax, [rbp+0D0h+var_B0]
0x14000494e  mov     [rbp+0D0h+var_120], rax
0x140004952  lea     rcx, [rbp+0D0h+var_B0]; this
0x140004956  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x14000495b  mov     r15, rax
0x14000495e  lea     rax, [rbp+0D0h+var_C0]
0x140004962  mov     [rbp+0D0h+var_128], rax
0x140004966  lea     rcx, [rbp+0D0h+var_C0]; this
0x14000496a  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x14000496f  mov     r14, rax
0x140004972  lea     rax, [rbp+0D0h+var_D0]
0x140004976  mov     [rbp+0D0h+var_130], rax
0x14000497a  mov     edx, edi
0x14000497c  lea     rcx, [rbp+0D0h+var_D0]
0x140004980  call    cs:__imp_??0CInsertionString@@QEAA@VCHex@@@Z; CInsertionString::CInsertionString(CHex)
0x140004986  mov     rsi, rax
0x140004989  lea     rax, [rbp+0D0h+var_E0]
0x14000498d  mov     [rbp+0D0h+var_138], rax
0x140004991  mov     rdx, [rbp+0D0h+arg_0]
0x140004998  mov     rdx, [rdx+8]; unsigned __int16 *
0x14000499c  lea     rcx, [rbp+0D0h+var_E0]; this
0x1400049a0  call    ??0CInsertionString@@QEAA@PEBG@Z; CInsertionString::CInsertionString(ushort const *)
0x1400049a5  mov     rdi, rax
0x1400049a8  lea     rax, [rbp+0D0h+var_F0]
0x1400049ac  mov     [rbp+0D0h+var_140], rax
0x1400049b0  lea     rdx, aWin32Perfrawda; "Win32_PerfRawData"
0x1400049b7  lea     rcx, [rbp+0D0h+var_F0]; this
0x1400049bb  call    ??0CInsertionString@@QEAA@PEBG@Z; CInsertionString::CInsertionString(ushort const *)
0x1400049c0  nop
0x1400049c1  mov     rcx, [rsp+78h]
0x1400049c6  mov     qword ptr [rsp+1D0h+var_178], rcx
0x1400049cb  mov     rcx, [rsp+1D0h+var_160]
0x1400049d0  mov     [rsp+1D0h+var_180], rcx
0x1400049d5  mov     rcx, [rsp+1D0h+var_168]
0x1400049da  jmp     loc_140004B3D
0x1400049df  mov     rax, [rbp+0D0h+arg_20]
0x1400049e6  mov     dword ptr [rax], 1
0x1400049ec  mov     [rbp+0D0h+var_150], 0
0x1400049f4  mov     rax, [rsi]
0x1400049f7  mov     [rsp+1D0h+var_1A8], 0
0x140004a00  lea     rcx, [rbp+0D0h+var_150]
0x140004a04  mov     [rsp+1D0h+var_1B0], rcx
0x140004a09  xor     r9d, r9d
0x140004a0c  xor     r8d, r8d
0x140004a0f  mov     rdx, r15
0x140004a12  mov     rcx, rsi
0x140004a15  mov     rax, [rax+30h]
0x140004a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a1e  mov     edi, eax
0x140004a20  mov     dword ptr [rsp+1D0h+var_170], eax
0x140004a24  test    eax, eax
0x140004a26  js      short loc_140004A43
0x140004a28  mov     rcx, [r14]
0x140004a2b  mov     rax, [rcx]
0x140004a2e  mov     rax, [rax+10h]
0x140004a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a37  mov     rax, [rbp+0D0h+var_150]
0x140004a3b  mov     [r14], rax
0x140004a3e  jmp     loc_140004B71
0x140004a43  lea     rax, [rbp+0D0h+var_60]
0x140004a47  mov     [rbp+0D0h+var_F8], rax
0x140004a4b  lea     rcx, [rbp+0D0h+var_60]; this
0x140004a4f  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140004a54  mov     [rsp+78h], rax
0x140004a59  lea     rax, [rbp+0D0h+var_70]
0x140004a5d  mov     [rbp+0D0h+var_100], rax
0x140004a61  lea     rcx, [rbp+0D0h+var_70]; this
0x140004a65  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140004a6a  mov     [rsp+1D0h+var_160], rax
0x140004a6f  lea     rax, [rbp+0D0h+var_80]
0x140004a73  mov     [rbp+0D0h+var_108], rax
0x140004a77  lea     rcx, [rbp+0D0h+var_80]; this
0x140004a7b  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140004a80  mov     [rsp+1D0h+var_168], rax
0x140004a85  lea     rax, [rbp+0D0h+var_90]
0x140004a89  mov     [rbp+0D0h+var_110], rax
0x140004a8d  lea     rcx, [rbp+0D0h+var_90]; this
0x140004a91  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140004a96  mov     r13, rax
0x140004a99  lea     rax, [rbp+0D0h+var_A0]
0x140004a9d  mov     [rbp+0D0h+var_118], rax
0x140004aa1  lea     rcx, [rbp+0D0h+var_A0]; this
0x140004aa5  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140004aaa  mov     r12, rax
0x140004aad  lea     rax, [rbp+0D0h+var_B0]
0x140004ab1  mov     [rbp+0D0h+var_120], rax
0x140004ab5  lea     rcx, [rbp+0D0h+var_B0]; this
0x140004ab9  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140004abe  mov     r15, rax
0x140004ac1  lea     rax, [rbp+0D0h+var_C0]
0x140004ac5  mov     [rbp+0D0h+var_128], rax
0x140004ac9  lea     rcx, [rbp+0D0h+var_C0]; this
0x140004acd  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140004ad2  mov     r14, rax
0x140004ad5  lea     rax, [rbp+0D0h+var_D0]
0x140004ad9  mov     [rbp+0D0h+var_130], rax
0x140004add  mov     edx, edi
0x140004adf  lea     rcx, [rbp+0D0h+var_D0]
0x140004ae3  call    cs:__imp_??0CInsertionString@@QEAA@VCHex@@@Z; CInsertionString::CInsertionString(CHex)
0x140004ae9  mov     rsi, rax
0x140004aec  lea     rax, [rbp+0D0h+var_E0]
0x140004af0  mov     [rbp+0D0h+var_138], rax
0x140004af4  mov     rax, [rbp+0D0h+arg_0]
0x140004afb  mov     rdx, [rax+8]; unsigned __int16 *
0x140004aff  lea     rcx, [rbp+0D0h+var_E0]; this
  ... truncated ...
```
