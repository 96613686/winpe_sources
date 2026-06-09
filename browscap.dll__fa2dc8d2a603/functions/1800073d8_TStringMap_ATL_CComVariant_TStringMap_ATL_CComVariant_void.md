# TStringMap<ATL::CComVariant>::~TStringMap<ATL::CComVariant>(void)

- ea: `0x1800073d8`
- end: `0x180007425`
- name: `??1?$TStringMap@VCComVariant@ATL@@@@QEAA@XZ`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bd5b`

## callees

- `0x180002498`
- `0x1800073d8`

## import_xrefs

- `msvcrt!free` at `0x180007414`
- `msvcrt!free` at `0x180007414`
- `OLEAUT32!__imp_VariantClear` at `0x1800073f3`
- `OLEAUT32!__imp_VariantClear` at `0x1800073f3`

## pseudocode

```c
void __fastcall TStringMap<ATL::CComVariant>::~TStringMap<ATL::CComVariant>(__int64 a1)
{
  __int64 i; // rbx
  void *v3; // rcx

  for ( i = *(_QWORD *)(a1 + 8); i != *(_QWORD *)(a1 + 16); i += 40 )
  {
    VariantClear((VARIANTARG *)(i + 16));
    TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(i);
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    free(v3);
}

```

## disassembly

```asm
0x1800073d8  mov     [rsp+arg_0], rbx
0x1800073dd  push    rdi
0x1800073de  sub     rsp, 20h
0x1800073e2  mov     rbx, [rcx+8]
0x1800073e6  mov     rdi, rcx
0x1800073e9  cmp     rbx, [rcx+10h]
0x1800073ed  jz      short loc_18000740B
0x1800073ef  lea     rcx, [rbx+10h]; pvarg
0x1800073f3  call    cs:__imp_VariantClear
0x1800073f9  mov     rcx, rbx
0x1800073fc  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x180007401  add     rbx, 28h ; '('
0x180007405  cmp     rbx, [rdi+10h]
0x180007409  jnz     short loc_1800073EF
0x18000740b  mov     rcx, [rdi+8]; Block
0x18000740f  test    rcx, rcx
0x180007412  jz      short loc_18000741A
0x180007414  call    cs:__imp_free
0x18000741a  mov     rbx, [rsp+28h+arg_0]
0x18000741f  add     rsp, 20h
0x180007423  pop     rdi
0x180007424  retn
```
