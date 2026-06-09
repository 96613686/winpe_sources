# CWMIBroker::HandleConnectServerFailure(long)

- ea: `0x140003360`
- end: `0x1400034c6`
- name: `?HandleConnectServerFailure@CWMIBroker@@EEAAXJ@Z`
- size: `358`
- prototype: `void __fastcall(const unsigned __int16 **this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002b5c`
- `0x140002de4`
- `0x140002e14`

## import_xrefs

- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x14000343d`
- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x14000343d`

## pseudocode

```c
void __fastcall CWMIBroker::HandleConnectServerFailure(const unsigned __int16 **this, unsigned int a2)
{
  CInsertionString *v3; // r13
  CInsertionString *v4; // r12
  CInsertionString *v5; // r15
  CInsertionString *v6; // r14
  CInsertionString *v7; // rsi
  CInsertionString *v8; // rdi
  __int64 v9; // rbx
  CInsertionString *v10; // rax
  _BYTE v11[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v12[16]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v13[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v14[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v15[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v16[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v17[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v18[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v19[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v20[64]; // [rsp+140h] [rbp+40h] BYREF
  CInsertionString *v22; // [rsp+1A0h] [rbp+A0h]
  CInsertionString *v23; // [rsp+1A8h] [rbp+A8h]

  v22 = CInsertionString::CInsertionString((CInsertionString *)v11);
  v23 = CInsertionString::CInsertionString((CInsertionString *)v12);
  v3 = CInsertionString::CInsertionString((CInsertionString *)v13);
  v4 = CInsertionString::CInsertionString((CInsertionString *)v14);
  v5 = CInsertionString::CInsertionString((CInsertionString *)v15);
  v6 = CInsertionString::CInsertionString((CInsertionString *)v16);
  v7 = CInsertionString::CInsertionString((CInsertionString *)v17);
  v8 = CInsertionString::CInsertionString((CInsertionString *)v18);
  v9 = CInsertionString::CInsertionString(v19, a2);
  v10 = CInsertionString::CInsertionString((CInsertionString *)v20, this[1]);
  CAdapUtility::NTLogEvent(
    v23,
    WBEM_MC_ADAP_CONNECTION_FAILURE,
    v10,
    v9,
    v8,
    v7,
    v6,
    v5,
    v4,
    v3,
    v23,
    v22,
    v11,
    v12,
    v13,
    v14,
    v15,
    v16,
    v17,
    v18);
}

```

## disassembly

```asm
0x140003360  mov     [rsp-8+arg_8], rbx
0x140003365  mov     [rsp-8+arg_0], rcx
0x14000336a  push    rbp
0x14000336b  push    rsi
0x14000336c  push    rdi
0x14000336d  push    r12
0x14000336f  push    r13
0x140003371  push    r14
0x140003373  push    r15
0x140003375  lea     rbp, [rsp-50h]
0x14000337a  sub     rsp, 150h
0x140003381  mov     ebx, edx
0x140003383  lea     rax, [rbp+80h+var_D0]
0x140003387  mov     [rsp+180h+var_120], rax
0x14000338c  lea     rcx, [rbp+80h+var_D0]; this
0x140003390  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140003395  mov     [rbp+80h+arg_10], rax
0x14000339c  lea     rax, [rbp+80h+var_C0]
0x1400033a0  mov     [rsp+180h+var_118], rax
0x1400033a5  lea     rcx, [rbp+80h+var_C0]; this
0x1400033a9  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1400033ae  mov     [rbp+80h+arg_18], rax
0x1400033b5  lea     rax, [rbp+80h+var_B0]
0x1400033b9  mov     [rsp+180h+var_110], rax
0x1400033be  lea     rcx, [rbp+80h+var_B0]; this
0x1400033c2  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1400033c7  mov     r13, rax
0x1400033ca  lea     rax, [rbp+80h+var_A0]
0x1400033ce  mov     [rsp+180h+var_108], rax
0x1400033d3  lea     rcx, [rbp+80h+var_A0]; this
0x1400033d7  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1400033dc  mov     r12, rax
0x1400033df  lea     rax, [rbp+80h+var_90]
0x1400033e3  mov     [rbp+80h+var_100], rax
0x1400033e7  lea     rcx, [rbp+80h+var_90]; this
0x1400033eb  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x1400033f0  mov     r15, rax
0x1400033f3  lea     rax, [rbp+80h+var_80]
0x1400033f7  mov     [rbp+80h+var_F8], rax
0x1400033fb  lea     rcx, [rbp+80h+var_80]; this
0x1400033ff  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140003404  mov     r14, rax
0x140003407  lea     rax, [rbp+80h+var_70]
0x14000340b  mov     [rbp+80h+var_F0], rax
0x14000340f  lea     rcx, [rbp+80h+var_70]; this
0x140003413  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140003418  mov     rsi, rax
0x14000341b  lea     rax, [rbp+80h+var_60]
0x14000341f  mov     [rbp+80h+var_E8], rax
0x140003423  lea     rcx, [rbp+80h+var_60]; this
0x140003427  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x14000342c  mov     rdi, rax
0x14000342f  lea     rax, [rbp+80h+var_50]
0x140003433  mov     [rbp+80h+var_E0], rax
0x140003437  mov     edx, ebx
0x140003439  lea     rcx, [rbp+80h+var_50]
0x14000343d  call    cs:__imp_??0CInsertionString@@QEAA@VCHex@@@Z; CInsertionString::CInsertionString(CHex)
0x140003443  mov     rbx, rax
0x140003446  lea     rax, [rbp+80h+var_40]
0x14000344a  mov     [rbp+80h+var_D8], rax
0x14000344e  mov     rdx, [rbp+80h+arg_0]
0x140003455  mov     rdx, [rdx+8]; unsigned __int16 *
0x140003459  lea     rcx, [rbp+80h+var_40]; this
0x14000345d  call    ??0CInsertionString@@QEAA@PEBG@Z; CInsertionString::CInsertionString(ushort const *)
0x140003462  nop
0x140003463  mov     rcx, [rbp+80h+arg_10]
0x14000346a  mov     [rsp+180h+var_128], rcx
0x14000346f  mov     rcx, [rbp+80h+arg_18]
0x140003476  mov     [rsp+180h+var_130], rcx
0x14000347b  mov     [rsp+180h+var_138], r13
0x140003480  mov     [rsp+180h+var_140], r12
0x140003485  mov     [rsp+180h+var_148], r15
0x14000348a  mov     [rsp+180h+var_150], r14
0x14000348f  mov     [rsp+180h+var_158], rsi
0x140003494  mov     [rsp+180h+var_160], rdi
0x140003499  mov     r9, rbx
0x14000349c  mov     r8, rax
0x14000349f  lea     rdx, WBEM_MC_ADAP_CONNECTION_FAILURE
0x1400034a6  call    ?NTLogEvent@CAdapUtility@@SAJKAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z; CAdapUtility::NTLogEvent(ulong,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)
0x1400034ab  mov     rbx, [rsp+180h+arg_8]
0x1400034b3  add     rsp, 150h
0x1400034ba  pop     r15
0x1400034bc  pop     r14
0x1400034be  pop     r13
0x1400034c0  pop     r12
0x1400034c2  pop     rdi
0x1400034c3  pop     rsi
0x1400034c4  pop     rbp
0x1400034c5  retn
```
