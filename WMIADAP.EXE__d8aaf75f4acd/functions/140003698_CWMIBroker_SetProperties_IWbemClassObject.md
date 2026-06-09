# CWMIBroker::SetProperties(IWbemClassObject *)

- ea: `0x140003698`
- end: `0x1400037de`
- name: `?SetProperties@CWMIBroker@@AEAAJPEAUIWbemClassObject@@@Z`
- size: `326`
- prototype: `__int64 __fastcall(CWMIBroker *__hidden this, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400037f0`

## callees

- `0x140002f30`
- `0x140003698`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1400036af`
- `OLEAUT32!__imp_VariantInit` at `0x1400036af`

## pseudocode

```c
__int64 __fastcall CWMIBroker::SetProperties(CWMIBroker *this, struct IWbemClassObject *a2)
{
  int v3; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF

  VariantInit(&pvarg);
  pvarg.vt = 1;
  pvarg.llVal = 0;
  v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, int))a2->lpVtbl->Put)(
         a2,
         L"Frequency_PerfTime",
         0,
         &pvarg,
         21);
  if ( v3 >= 0 )
  {
    v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, int))a2->lpVtbl->Put)(
           a2,
           L"Timestamp_PerfTime",
           0,
           &pvarg,
           21);
    if ( v3 >= 0 )
    {
      v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, int))a2->lpVtbl->Put)(
             a2,
             L"Timestamp_Sys100NS",
             0,
             &pvarg,
             21);
      if ( v3 >= 0 )
      {
        v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, int))a2->lpVtbl->Put)(
               a2,
               L"Frequency_Sys100NS",
               0,
               &pvarg,
               21);
        if ( v3 >= 0 )
        {
          v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, int))a2->lpVtbl->Put)(
                 a2,
                 L"Frequency_Object",
                 0,
                 &pvarg,
                 21);
          if ( v3 >= 0 )
            v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, int))a2->lpVtbl->Put)(
                   a2,
                   L"Timestamp_Object",
                   0,
                   &pvarg,
                   21);
        }
      }
    }
  }
  _variant_t::~_variant_t(&pvarg);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140003698  mov     [rsp+arg_0], rbx
0x14000369d  mov     [rsp+arg_8], rsi
0x1400036a2  push    rdi
0x1400036a3  sub     rsp, 50h
0x1400036a7  mov     rdi, rdx
0x1400036aa  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1400036af  call    cs:__imp_VariantInit
0x1400036b5  nop
0x1400036b6  mov     eax, 1
0x1400036bb  mov     word ptr [rsp+58h+pvarg], ax
0x1400036c0  mov     qword ptr [rsp+58h+pvarg+8], 0
0x1400036c9  mov     rax, [rdi]
0x1400036cc  mov     esi, 15h
0x1400036d1  mov     [rsp+58h+var_38], esi
0x1400036d5  lea     r9, [rsp+58h+pvarg]
0x1400036da  xor     r8d, r8d
0x1400036dd  lea     rdx, aFrequencyPerft; "Frequency_PerfTime"
0x1400036e4  mov     rcx, rdi
0x1400036e7  mov     rax, [rax+28h]
0x1400036eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036f0  mov     ebx, eax
0x1400036f2  test    eax, eax
0x1400036f4  js      loc_1400037C2
0x1400036fa  mov     rax, [rdi]
0x1400036fd  mov     [rsp+58h+var_38], esi
0x140003701  lea     r9, [rsp+58h+pvarg]
0x140003706  xor     r8d, r8d
0x140003709  lea     rdx, aTimestampPerft; "Timestamp_PerfTime"
0x140003710  mov     rcx, rdi
0x140003713  mov     rax, [rax+28h]
0x140003717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000371c  mov     ebx, eax
0x14000371e  test    eax, eax
0x140003720  js      loc_1400037C2
0x140003726  mov     rax, [rdi]
0x140003729  mov     [rsp+58h+var_38], esi
0x14000372d  lea     r9, [rsp+58h+pvarg]
0x140003732  xor     r8d, r8d
0x140003735  lea     rdx, aTimestampSys10; "Timestamp_Sys100NS"
0x14000373c  mov     rcx, rdi
0x14000373f  mov     rax, [rax+28h]
0x140003743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003748  mov     ebx, eax
0x14000374a  test    eax, eax
0x14000374c  js      short loc_1400037C2
0x14000374e  mov     rax, [rdi]
0x140003751  mov     [rsp+58h+var_38], esi
0x140003755  lea     r9, [rsp+58h+pvarg]
0x14000375a  xor     r8d, r8d
0x14000375d  lea     rdx, aFrequencySys10; "Frequency_Sys100NS"
0x140003764  mov     rcx, rdi
0x140003767  mov     rax, [rax+28h]
0x14000376b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003770  mov     ebx, eax
0x140003772  test    eax, eax
0x140003774  js      short loc_1400037C2
0x140003776  mov     rax, [rdi]
0x140003779  mov     [rsp+58h+var_38], esi
0x14000377d  lea     r9, [rsp+58h+pvarg]
0x140003782  xor     r8d, r8d
0x140003785  lea     rdx, aFrequencyObjec; "Frequency_Object"
0x14000378c  mov     rcx, rdi
0x14000378f  mov     rax, [rax+28h]
0x140003793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003798  mov     ebx, eax
0x14000379a  test    eax, eax
0x14000379c  js      short loc_1400037C2
0x14000379e  mov     rax, [rdi]
0x1400037a1  mov     [rsp+58h+var_38], esi
0x1400037a5  lea     r9, [rsp+58h+pvarg]
0x1400037aa  xor     r8d, r8d
0x1400037ad  lea     rdx, aTimestampObjec; "Timestamp_Object"
0x1400037b4  mov     rcx, rdi
0x1400037b7  mov     rax, [rax+28h]
0x1400037bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037c0  mov     ebx, eax
0x1400037c2  lea     rcx, [rsp+58h+pvarg]; this
0x1400037c7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1400037cc  mov     eax, ebx
0x1400037ce  mov     rbx, [rsp+58h+arg_0]
0x1400037d3  mov     rsi, [rsp+58h+arg_8]
0x1400037d8  add     rsp, 50h
0x1400037dc  pop     rdi
0x1400037dd  retn
```
