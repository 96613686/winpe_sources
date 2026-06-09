# WTL::CPropertySheetImpl<CFoDWizard,WTL::CPropertySheetWindow>::DoModal(HWND__ *)

- ea: `0x180024c44`
- end: `0x180024d14`
- name: `?DoModal@?$CPropertySheetImpl@VCFoDWizard@@VCPropertySheetWindow@WTL@@@WTL@@QEAA_JPEAUHWND__@@@Z`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180029208`
- `0x18002940c`

## callees

- `0x180024038`
- `0x180024c44`
- `0x180026538`
- `0x180027d34`
- `0x180056720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024d0d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024d0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024c87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024c87`

## pseudocode

```c
INT_PTR __fastcall WTL::CPropertySheetImpl<CFoDWizard,WTL::CPropertySheetWindow>::DoModal(__int64 a1, __int64 a2)
{
  __int64 v3; // r14
  _QWORD *v4; // rbx
  INT_PTR v5; // rax
  INT_PTR v6; // rbx
  __int64 *v8; // [rsp+20h] [rbp-38h] BYREF
  char v9; // [rsp+28h] [rbp-30h]

  *(_DWORD *)(a1 + 76) &= ~0x400u;
  if ( !*(_QWORD *)(a1 + 80) )
    *(_QWORD *)(a1 + 80) = a2;
  v3 = a1 + 168;
  v4 = (_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 128) = *(_QWORD *)(a1 + 168);
  *(_DWORD *)(a1 + 112) = *(_DWORD *)(a1 + 176);
  if ( a1 == -16 )
  {
    RaiseException(0xC0000005, 1u, 0, 0);
    JUMPOUT(0x180024D13LL);
  }
  *v4 = a1;
  v9 = 0;
  *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
  v8 = qword_180078238;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v8) >= 0 )
  {
    v4[2] = qword_180078260;
    qword_180078260 = (__int64)v4;
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v8);
  v5 = PropertySheetW((LPCPROPSHEETHEADERW)(a1 + 72));
  *(_DWORD *)(a1 + 112) = 0;
  v6 = v5;
  *(_QWORD *)(a1 + 128) = 0;
  ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(v3);
  return v6;
}

```

## disassembly

```asm
0x180024c44  push    rbx
0x180024c46  push    rsi
0x180024c47  push    rdi
0x180024c48  push    r14
0x180024c4a  sub     rsp, 38h
0x180024c4e  btr     dword ptr [rcx+4Ch], 0Ah
0x180024c53  mov     rdi, rcx
0x180024c56  cmp     qword ptr [rcx+50h], 0
0x180024c5b  jnz     short loc_180024C61
0x180024c5d  mov     [rcx+50h], rdx
0x180024c61  lea     r14, [rcx+0A8h]
0x180024c68  mov     rax, [r14]
0x180024c6b  lea     rbx, [rcx+10h]
0x180024c6f  mov     [rcx+80h], rax
0x180024c76  mov     eax, [rcx+0B0h]
0x180024c7c  mov     [rcx+70h], eax
0x180024c7f  test    rbx, rbx
0x180024c82  jz      short loc_180024CFE
0x180024c84  mov     [rbx], rdi
0x180024c87  call    cs:__imp_GetCurrentThreadId
0x180024c8d  lea     rcx, [rsp+58h+var_38]
0x180024c92  mov     [rsp+58h+var_30], 0
0x180024c97  mov     [rbx+8], eax
0x180024c9a  lea     rax, qword_180078238
0x180024ca1  mov     [rsp+58h+var_38], rax
0x180024ca6  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180024cab  test    eax, eax
0x180024cad  js      short loc_180024CC1
0x180024caf  mov     rax, cs:qword_180078260
0x180024cb6  mov     [rbx+10h], rax
0x180024cba  mov     cs:qword_180078260, rbx
0x180024cc1  lea     rcx, [rsp+58h+var_38]
0x180024cc6  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180024ccb  lea     rcx, [rdi+48h]; LPCPROPSHEETHEADERW
0x180024ccf  call    PropertySheetW
0x180024cd4  mov     rcx, r14
0x180024cd7  mov     dword ptr [rdi+70h], 0
0x180024cde  mov     rbx, rax
0x180024ce1  mov     qword ptr [rdi+80h], 0
0x180024cec  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180024cf1  mov     rax, rbx
0x180024cf4  add     rsp, 38h
0x180024cf8  pop     r14
0x180024cfa  pop     rdi
0x180024cfb  pop     rsi
0x180024cfc  pop     rbx
0x180024cfd  retn
0x180024cfe  xor     r9d, r9d; lpArguments
0x180024d01  xor     r8d, r8d; nNumberOfArguments
0x180024d04  mov     ecx, 0C0000005h; dwExceptionCode
0x180024d09  lea     edx, [r9+1]; dwExceptionFlags
0x180024d0d  call    cs:__imp_RaiseException
```
