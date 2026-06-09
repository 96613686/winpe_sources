# GetComputerDN

- ea: `0x180024498`
- end: `0x18002474e`
- name: `GetComputerDN`
- size: `694`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180023f54`
- `0x18002561c`

## callees

- `0x180004d91`
- `0x18000d1f0`
- `0x18000f35c`
- `0x18000f7e4`
- `0x180011578`
- `0x180024498`
- `0x180025368`
- `0x180025454`
- `0x18002c4dc`
- `0x18002c6c8`
- `0x18009bd1c`
- `0x1800d08f8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180024515`
- `KERNEL32!GetLastError` at `0x180024697`
- `KERNEL32!GetLastError` at `0x180024515`
- `KERNEL32!GetLastError` at `0x180024697`
- `KERNEL32!Sleep` at `0x18002458b`
- `KERNEL32!Sleep` at `0x18002458b`
- `Secur32!GetComputerObjectNameW` at `0x18002450f`
- `Secur32!GetComputerObjectNameW` at `0x18002468d`
- `Secur32!GetComputerObjectNameW` at `0x18002450f`
- `Secur32!GetComputerObjectNameW` at `0x18002468d`
- `mqsec!MQSec_IsDC` at `0x1800244b5`
- `mqsec!MQSec_IsDC` at `0x1800244b5`

## pseudocode

```c
void __fastcall GetComputerDN(WCHAR **a1, ULONG *a2)
{
  signed int LastError; // ebx
  unsigned int v5; // esi
  PVOID *v6; // rcx
  unsigned int i; // edi
  WCHAR *v8; // rax
  DWORD v9; // eax
  signed int v10; // ebx
  _BYTE pExceptionObject[88]; // [rsp+20h] [rbp-58h] BYREF

  LastError = 0;
  *a2 = 0;
  v5 = 5;
  if ( MQSec_IsDC() )
  {
    v5 = 300;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_6;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_f073386f5643352810e6d9a62b947684_Traceguids, 300);
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_6:
  for ( i = 0; i < v5; ++i )
  {
    GetComputerObjectNameW(NameFullyQualifiedDN, 0, a2);
    LastError = GetLastError();
    if ( LastError != 1355 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      break;
    }
    if ( (unsigned __int8)NT4Domain() )
    {
      RemoveADIntegrated();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_f073386f5643352810e6d9a62b947684_Traceguids);
      LogIllegalPoint((wchar_t *)L"joinstat", 0x5DDu);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, -1073739658);
      throw (bad_hresult *)pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_f073386f5643352810e6d9a62b947684_Traceguids, i);
    if ( i )
      LogMsgNTStatus(i, (wchar_t *)L"joinstat", 0x131u);
    LODWORD(qword_1801291DC) = qword_1801291DC + 1;
    HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
    SetStatus();
    Sleep(0x3E8u);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*a2 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
      WPP_SF_d(v6[2], 28, &WPP_f073386f5643352810e6d9a62b947684_Traceguids, (unsigned int)LastError);
    LogIllegalPoint((wchar_t *)L"joinstat", 0x136u);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, LastError);
    throw (bad_hresult *)pExceptionObject;
  }
  v8 = (WCHAR *)MmAllocate(saturated_mul(*a2, 2u));
  *a1 = v8;
  if ( !GetComputerObjectNameW(NameFullyQualifiedDN, v8, a2) )
  {
    v9 = GetLastError();
    v10 = v9;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_f073386f5643352810e6d9a62b947684_Traceguids, v9);
    LogIllegalPoint((wchar_t *)L"joinstat", 0x140u);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v10);
    throw (bad_hresult *)pExceptionObject;
  }
  LODWORD(qword_1801291DC) = qword_1801291DC + 1;
  HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
  SetStatus();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
}

```

## disassembly

```asm
0x180024498  push    rbx
0x18002449a  push    rsi
0x18002449b  push    rdi
0x18002449c  push    r12
0x18002449e  push    r13
0x1800244a0  push    r14
0x1800244a2  push    r15
0x1800244a4  sub     rsp, 40h
0x1800244a8  xor     ebx, ebx
0x1800244aa  mov     r14, rdx
0x1800244ad  mov     r15, rcx
0x1800244b0  mov     [rdx], ebx
0x1800244b2  lea     esi, [rbx+5]
0x1800244b5  call    cs:__imp_?MQSec_IsDC@@YA_NXZ; MQSec_IsDC(void)
0x1800244bb  lea     r13, WPP_f073386f5643352810e6d9a62b947684_Traceguids
0x1800244c2  lea     r12, WPP_GLOBAL_Control
0x1800244c9  test    al, al
0x1800244cb  jz      short loc_1800244F6
0x1800244cd  mov     esi, 12Ch
0x1800244d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244d9  cmp     rcx, r12
0x1800244dc  jz      short loc_1800244FD
0x1800244de  test    byte ptr [rcx+1Ch], 4
0x1800244e2  jz      short loc_1800244FD
0x1800244e4  mov     rcx, [rcx+10h]
0x1800244e8  lea     edx, [rbx+19h]
0x1800244eb  mov     r9d, esi
0x1800244ee  mov     r8, r13
0x1800244f1  call    WPP_SF_d
0x1800244f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244fd  xor     edi, edi
0x1800244ff  cmp     edi, esi
0x180024501  jnb     loc_180024600
0x180024507  xor     edx, edx; lpNameBuffer
0x180024509  mov     r8, r14; nSize
0x18002450c  lea     ecx, [rdx+1]; NameFormat
0x18002450f  call    cs:__imp_GetComputerObjectNameW
0x180024515  call    cs:__imp_GetLastError
0x18002451b  mov     ebx, eax
0x18002451d  cmp     eax, 54Bh
0x180024522  jnz     loc_1800245F9
0x180024528  call    NT4Domain
0x18002452d  test    al, al
0x18002452f  jnz     short loc_18002459F
0x180024531  mov     rcx, cs:WPP_GLOBAL_Control
0x180024538  cmp     rcx, r12
0x18002453b  jz      short loc_180024557
0x18002453d  test    byte ptr [rcx+1Ch], 2
0x180024541  jz      short loc_180024557
0x180024543  mov     rcx, [rcx+10h]
0x180024547  mov     edx, 1Bh
0x18002454c  mov     r9d, edi
0x18002454f  mov     r8, r13
0x180024552  call    WPP_SF_d
0x180024557  test    edi, edi
0x180024559  jz      short loc_18002456F
0x18002455b  mov     r8d, 131h; unsigned __int16
0x180024561  lea     rdx, aJoinstat; "joinstat"
0x180024568  mov     ecx, edi; int
0x18002456a  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18002456f  mov     eax, cs:?g_ServiceProgressTime@@3KA; ulong g_ServiceProgressTime
0x180024575  inc     dword ptr cs:qword_1801291DC
0x18002457b  mov     dword ptr cs:qword_1801291DC+4, eax
0x180024581  call    ?SetStatus@@YAXXZ; SetStatus(void)
0x180024586  mov     ecx, 3E8h; dwMilliseconds
0x18002458b  call    cs:__imp_Sleep
0x180024591  mov     rcx, cs:WPP_GLOBAL_Control
0x180024598  inc     edi
0x18002459a  jmp     loc_1800244FF
0x18002459f  call    RemoveADIntegrated
0x1800245a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245ab  cmp     rcx, r12
0x1800245ae  jz      short loc_1800245C7
0x1800245b0  test    byte ptr [rcx+1Ch], 1
0x1800245b4  jz      short loc_1800245C7
0x1800245b6  mov     rcx, [rcx+10h]
0x1800245ba  mov     edx, 1Ah
0x1800245bf  mov     r8, r13
0x1800245c2  call    WPP_SF_
0x1800245c7  mov     edx, 5DDh; unsigned __int16
0x1800245cc  lea     rcx, aJoinstat; "joinstat"
0x1800245d3  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x1800245d8  mov     edx, 0C0000876h; unsigned int
0x1800245dd  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800245e2  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800245e7  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x1800245ee  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800245f3  call    _CxxThrowException_0
0x1800245f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180024600  cmp     dword ptr [r14], 0
0x180024604  jnz     short loc_180024661
0x180024606  cmp     rcx, r12
0x180024609  jz      short loc_180024625
0x18002460b  test    byte ptr [rcx+1Ch], 1
0x18002460f  jz      short loc_180024625
0x180024611  mov     rcx, [rcx+10h]
0x180024615  mov     edx, 1Ch
0x18002461a  mov     r9d, ebx
0x18002461d  mov     r8, r13
0x180024620  call    WPP_SF_d
0x180024625  mov     edx, 136h; unsigned __int16
0x18002462a  lea     rcx, aJoinstat; "joinstat"
0x180024631  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x180024636  test    ebx, ebx
0x180024638  jle     short loc_180024643
0x18002463a  movzx   ebx, bx
0x18002463d  or      ebx, 80070000h
0x180024643  mov     edx, ebx; unsigned int
0x180024645  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18002464a  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18002464f  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180024656  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18002465b  call    _CxxThrowException_0
0x180024661  mov     ecx, [r14]
0x180024664  mov     eax, 2
0x180024669  mul     rcx
0x18002466c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180024673  cmovb   rax, rcx
0x180024677  mov     rcx, rax; unsigned __int64
0x18002467a  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18002467f  mov     r8, r14; nSize
0x180024682  mov     [r15], rax
0x180024685  mov     rdx, rax; lpNameBuffer
0x180024688  mov     ecx, 1; NameFormat
0x18002468d  call    cs:__imp_GetComputerObjectNameW
0x180024693  test    al, al
0x180024695  jnz     short loc_180024701
0x180024697  call    cs:__imp_GetLastError
0x18002469d  mov     ebx, eax
0x18002469f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246a6  cmp     rcx, r12
0x1800246a9  jz      short loc_1800246C5
0x1800246ab  test    byte ptr [rcx+1Ch], 1
0x1800246af  jz      short loc_1800246C5
0x1800246b1  mov     rcx, [rcx+10h]
0x1800246b5  mov     edx, 1Dh
0x1800246ba  mov     r9d, eax
0x1800246bd  mov     r8, r13
0x1800246c0  call    WPP_SF_d
0x1800246c5  mov     edx, 140h; unsigned __int16
0x1800246ca  lea     rcx, aJoinstat; "joinstat"
0x1800246d1  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x1800246d6  test    ebx, ebx
0x1800246d8  jle     short loc_1800246E3
0x1800246da  movzx   ebx, bx
0x1800246dd  or      ebx, 80070000h
0x1800246e3  mov     edx, ebx; unsigned int
0x1800246e5  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800246ea  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800246ef  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x1800246f6  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800246fb  call    _CxxThrowException_0
0x180024701  mov     eax, cs:?g_ServiceProgressTime@@3KA; ulong g_ServiceProgressTime
0x180024707  inc     dword ptr cs:qword_1801291DC
0x18002470d  mov     dword ptr cs:qword_1801291DC+4, eax
0x180024713  call    ?SetStatus@@YAXXZ; SetStatus(void)
0x180024718  mov     rcx, cs:WPP_GLOBAL_Control
0x18002471f  cmp     rcx, r12
0x180024722  jz      short loc_18002473E
0x180024724  test    byte ptr [rcx+1Ch], 4
0x180024728  jz      short loc_18002473E
0x18002472a  mov     r9, [r15]
0x18002472d  mov     edx, 1Eh
0x180024732  mov     rcx, [rcx+10h]; LoggerHandle
0x180024736  mov     r8, r13
0x180024739  call    WPP_SF_S
0x18002473e  add     rsp, 40h
0x180024742  pop     r15
0x180024744  pop     r14
0x180024746  pop     r13
0x180024748  pop     r12
0x18002474a  pop     rdi
0x18002474b  pop     rsi
0x18002474c  pop     rbx
0x18002474d  retn
```
