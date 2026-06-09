# ShieldProvider::FreeMpSampleSubmissionConsent(tagMPSAMPLE_SUBMISSION_CONSENT *)

- ea: `0x18002eda0`
- end: `0x18002edd9`
- name: `?FreeMpSampleSubmissionConsent@ShieldProvider@@YAXPEAUtagMPSAMPLE_SUBMISSION_CONSENT@@@Z`
- size: `57`
- prototype: `void __fastcall(ShieldProvider *__hidden this, struct tagMPSAMPLE_SUBMISSION_CONSENT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800317e4`
- `0x180035108`

## callees

- `0x18002eda0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002edb5`
- `ole32!CoTaskMemFree` at `0x18002edc4`
- `ole32!CoTaskMemFree` at `0x18002edcd`
- `ole32!CoTaskMemFree` at `0x18002edb5`
- `ole32!CoTaskMemFree` at `0x18002edc4`
- `ole32!CoTaskMemFree` at `0x18002edcd`

## pseudocode

```c
void __fastcall ShieldProvider::FreeMpSampleSubmissionConsent(
        ShieldProvider *this,
        struct tagMPSAMPLE_SUBMISSION_CONSENT *a2)
{
  void *v3; // rcx
  void *v4; // rcx

  if ( this )
  {
    v3 = *(void **)this;
    if ( v3 )
      CoTaskMemFree(v3);
    v4 = (void *)*((_QWORD *)this + 1);
    if ( v4 )
      CoTaskMemFree(v4);
    CoTaskMemFree(this);
  }
}

```

## disassembly

```asm
0x18002eda0  test    rcx, rcx
0x18002eda3  jz      short locret_18002EDD8
0x18002eda5  push    rbx
0x18002eda6  sub     rsp, 20h
0x18002edaa  mov     rbx, rcx
0x18002edad  mov     rcx, [rcx]; pv
0x18002edb0  test    rcx, rcx
0x18002edb3  jz      short loc_18002EDBB
0x18002edb5  call    cs:__imp_CoTaskMemFree
0x18002edbb  mov     rcx, [rbx+8]; pv
0x18002edbf  test    rcx, rcx
0x18002edc2  jz      short loc_18002EDCA
0x18002edc4  call    cs:__imp_CoTaskMemFree
0x18002edca  mov     rcx, rbx; pv
0x18002edcd  call    cs:__imp_CoTaskMemFree
0x18002edd3  add     rsp, 20h
0x18002edd7  pop     rbx
0x18002edd8  retn
```
