# CApplication::LinkProcess(CProcess *)

- ea: `0x18000f080`
- end: `0x18000f250`
- name: `?LinkProcess@CApplication@@QEAAJPEAVCProcess@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(CApplication *__hidden this, struct CProcess *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000208c`
- `0x180002ebc`

## callees

- `0x180002fd4`
- `0x18000eb1c`
- `0x18000f080`
- `0x18000f5f4`
- `0x180019524`
- `0x1800270b8`
- `0x18003a5fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f0ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f0ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f238`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f238`

## string_xrefs

- `0x18000f21c`: `CApplication::LinkProcess`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CApplication::LinkProcess(CApplication *this, struct CProcess *a2)
{
  struct CProcess *v2; // r13
  CApplication *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // r15
  int v5; // r8d
  int v6; // r11d
  _DWORD *v7; // rcx
  _DWORD *v8; // rdx
  _DWORD *v9; // r9
  _DWORD *v10; // r10
  unsigned int v11; // r14d
  __int64 v12; // r12
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  ATL::CAtlException *v17; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+88h] [rbp+20h]

  v2 = a2;
  v3 = this;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v21 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *((_DWORD *)v3 + 162) = *((_DWORD *)v2 + 105);
  v5 = *((_DWORD *)v2 + 106);
  *((_DWORD *)v3 + 163) = v5;
  *((_BYTE *)v3 + 720) = *((_BYTE *)v2 + 786);
  *((_DWORD *)v3 + 164) |= *((_DWORD *)v2 + 111);
  v6 = *((_DWORD *)v3 + 164);
  v7 = (_DWORD *)((char *)v3 + 208);
  v8 = (_DWORD *)((char *)v3 + 216);
  v9 = (_DWORD *)((char *)v3 + 324);
  v10 = (_DWORD *)((char *)v3 + 328);
  if ( !v5 )
  {
    *v7 |= 1u;
    *v8 = 2;
    *v9 = 2;
    *v10 = 2;
  }
  if ( v6 )
  {
    *v7 |= 0x40u;
    *v8 = 2;
    *v9 = 2;
    *v10 = 2;
    *(_QWORD *)((char *)v3 + 620) = 0;
    *(_QWORD *)((char *)v3 + 628) = 0;
    *(_QWORD *)((char *)v3 + 636) = 0;
    *((_DWORD *)v3 + 161) = 1;
  }
  if ( !CApplication::GetActiveProcessCount(v3) )
    *((_DWORD *)v3 + 171) = 1;
  try
  {
    v11 = 0;
    v12 = *((_QWORD *)v3 + 9);
    ATL::CAtlList<CProcess *,ATL::CElementTraits<CProcess *>>::GetFreeNode((char *)v3 + 72);
    v13 = (__int64 *)*((_QWORD *)v3 + 13);
    v14 = *v13;
    v13[2] = (__int64)v2;
    *((_QWORD *)v3 + 13) = v14;
    v13[1] = 0;
    *v13 = v12;
    ++*((_QWORD *)v3 + 11);
    if ( *((_QWORD *)v3 + 9) )
      *(_QWORD *)(*((_QWORD *)v3 + 9) + 8LL) = v13;
    else
      *((_QWORD *)v3 + 10) = v13;
    *((_QWORD *)v3 + 9) = v13;
  }
  catch ( ATL::CAtlException *v17 )
  {
    if ( *(_DWORD *)v17 == -1073741571 )
      _o__resetstkoflw();
    v11 = (unsigned int)v4;
    if ( (int)v4 < 0 )
    {
      AudPolicyLogError("CApplication::LinkProcess", 281, (int)v4);
      v4 = v21;
      goto LABEL_17;
    }
    v3 = this;
    v2 = a2;
    v4 = v21;
  }
  v15 = CApplication::RegisterProcessWithApplicationSpecificEndpointInfo(v3, v2);
  if ( v15 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
      (const char *)(unsigned int)v15,
      (int)v17);
  wil::com_ptr_t<CApplication,wil::err_returncode_policy>::operator=((char *)v2 + 224, v3);
LABEL_17:
  if ( v4 )
    LeaveCriticalSection(v4);
  return v11;
}

```

## disassembly

```asm
0x18000f080  mov     [rsp+arg_8], rdx
0x18000f085  mov     [rsp+arg_0], rcx
0x18000f08a  push    rbx
0x18000f08b  push    rsi
0x18000f08c  push    r12
0x18000f08e  push    r13
0x18000f090  push    r14
0x18000f092  push    r15
0x18000f094  sub     rsp, 38h
0x18000f098  mov     r13, rdx
0x18000f09b  mov     rbx, rcx
0x18000f09e  lea     r15, [rcx+20h]
0x18000f0a2  mov     [rsp+68h+arg_18], r15
0x18000f0aa  mov     rcx, r15; lpCriticalSection
0x18000f0ad  call    cs:__imp_EnterCriticalSection
0x18000f0b3  mov     qword ptr [rsp+68h+arg_10], r15
0x18000f0bb  mov     eax, [r13+1A4h]
0x18000f0c2  mov     [rbx+288h], eax
0x18000f0c8  mov     r8d, [r13+1A8h]
0x18000f0cf  mov     [rbx+28Ch], r8d
0x18000f0d6  mov     al, [r13+312h]
0x18000f0dd  mov     [rbx+2D0h], al
0x18000f0e3  mov     eax, [r13+1BCh]
0x18000f0ea  or      [rbx+290h], eax
0x18000f0f0  mov     r11d, [rbx+290h]
0x18000f0f7  lea     rcx, [rbx+0D0h]
0x18000f0fe  lea     rdx, [rbx+0D8h]
0x18000f105  lea     r9, [rbx+144h]
0x18000f10c  lea     r10, [rbx+148h]
0x18000f113  mov     eax, 2
0x18000f118  test    r8d, r8d
0x18000f11b  jnz     short loc_18000F128
0x18000f11d  or      dword ptr [rcx], 1
0x18000f120  mov     [rdx], eax
0x18000f122  mov     [r9], eax
0x18000f125  mov     [r10], eax
0x18000f128  test    r11d, r11d
0x18000f12b  jz      short loc_18000F163
0x18000f12d  or      dword ptr [rcx], 40h
0x18000f130  mov     [rdx], eax
0x18000f132  mov     [r9], eax
0x18000f135  mov     [r10], eax
0x18000f138  mov     qword ptr [rbx+26Ch], 0
0x18000f143  mov     qword ptr [rbx+274h], 0
0x18000f14e  mov     qword ptr [rbx+27Ch], 0
0x18000f159  mov     dword ptr [rbx+284h], 1
0x18000f163  mov     rcx, rbx; this
0x18000f166  call    ?GetActiveProcessCount@CApplication@@QEAAIXZ; CApplication::GetActiveProcessCount(void)
0x18000f16b  test    eax, eax
0x18000f16d  jnz     short loc_18000F179
0x18000f16f  mov     dword ptr [rbx+2ACh], 1
0x18000f179  xor     r14d, r14d
0x18000f17c  lea     rsi, [rbx+48h]
0x18000f180  mov     r12, [rsi]
0x18000f183  mov     rcx, rsi
0x18000f186  call    ?GetFreeNode@?$CAtlList@PEAVCProcess@@V?$CElementTraits@PEAVCProcess@@@ATL@@@ATL@@AEAAXXZ; ATL::CAtlList<CProcess *,ATL::CElementTraits<CProcess *>>::GetFreeNode(void)
0x18000f18b  mov     rcx, [rsi+20h]
0x18000f18f  mov     rax, [rcx]
0x18000f192  mov     [rcx+10h], r13
0x18000f196  mov     [rsi+20h], rax
0x18000f19a  mov     [rcx+8], r14
0x18000f19e  mov     [rcx], r12
0x18000f1a1  inc     qword ptr [rsi+10h]
0x18000f1a5  mov     rax, [rsi]
0x18000f1a8  test    rax, rax
0x18000f1ab  jz      short loc_18000F1B3
0x18000f1ad  mov     [rax+8], rcx
0x18000f1b1  jmp     short loc_18000F1B7
0x18000f1b3  mov     [rsi+8], rcx
0x18000f1b7  mov     [rsi], rcx
0x18000f1ba  jmp     short loc_18000F1DB
0x18000f1bc  mov     r14d, [rsp+68h+arg_10]
0x18000f1c4  test    r14d, r14d
0x18000f1c7  js      short loc_18000F214
0x18000f1c9  mov     rbx, [rsp+68h+arg_0]
0x18000f1ce  mov     r13, [rsp+68h+arg_8]
0x18000f1d3  mov     r15, [rsp+68h+arg_18]
0x18000f1db  mov     rdx, r13; struct CProcess *
0x18000f1de  mov     rcx, rbx; this
0x18000f1e1  call    ?RegisterProcessWithApplicationSpecificEndpointInfo@CApplication@@QEAAJPEAVCProcess@@@Z; CApplication::RegisterProcessWithApplicationSpecificEndpointInfo(CProcess *)
0x18000f1e6  mov     rcx, [rsp+68h]; this
0x18000f1eb  test    eax, eax
0x18000f1ed  jns     short loc_18000F203
0x18000f1ef  mov     r9d, eax; char *
0x18000f1f2  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x18000f1f9  mov     edx, 112h; void *
0x18000f1fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f203  lea     rcx, [r13+0E0h]
0x18000f20a  mov     rdx, rbx
0x18000f20d  call    ??4?$com_ptr_t@VCApplication@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAVCApplication@@@Z; wil::com_ptr_t<CApplication,wil::err_returncode_policy>::operator=(CApplication *)
0x18000f212  jmp     short loc_18000F230
0x18000f214  mov     r8d, r14d; int
0x18000f217  mov     edx, 119h; int
0x18000f21c  lea     rcx, aCapplicationLi; "CApplication::LinkProcess"
0x18000f223  call    ?AudPolicyLogError@@YAXPEBDHJ@Z; AudPolicyLogError(char const *,int,long)
0x18000f228  mov     r15, [rsp+68h+arg_18]
0x18000f230  test    r15, r15
0x18000f233  jz      short loc_18000F23E
0x18000f235  mov     rcx, r15; lpCriticalSection
0x18000f238  call    cs:__imp_LeaveCriticalSection
0x18000f23e  mov     eax, r14d
0x18000f241  add     rsp, 38h
0x18000f245  pop     r15
0x18000f247  pop     r14
0x18000f249  pop     r13
0x18000f24b  pop     r12
0x18000f24d  pop     rsi
0x18000f24e  pop     rbx
0x18000f24f  retn
```
