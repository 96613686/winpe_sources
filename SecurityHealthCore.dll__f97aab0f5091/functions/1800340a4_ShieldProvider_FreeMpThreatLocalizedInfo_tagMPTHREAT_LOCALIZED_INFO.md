# ShieldProvider::FreeMpThreatLocalizedInfo(tagMPTHREAT_LOCALIZED_INFO *)

- ea: `0x1800340a4`
- end: `0x18003413c`
- name: `?FreeMpThreatLocalizedInfo@ShieldProvider@@YAXPEAUtagMPTHREAT_LOCALIZED_INFO@@@Z`
- size: `152`
- prototype: `void __fastcall(ShieldProvider *__hidden this, struct tagMPTHREAT_LOCALIZED_INFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800357d8`

## callees

- `0x1800340a4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800340be`
- `ole32!CoTaskMemFree` at `0x1800340cd`
- `ole32!CoTaskMemFree` at `0x1800340dc`
- `ole32!CoTaskMemFree` at `0x1800340eb`
- `ole32!CoTaskMemFree` at `0x1800340fa`
- `ole32!CoTaskMemFree` at `0x180034109`
- `ole32!CoTaskMemFree` at `0x180034118`
- `ole32!CoTaskMemFree` at `0x180034127`
- `ole32!CoTaskMemFree` at `0x180034130`
- `ole32!CoTaskMemFree` at `0x1800340be`
- `ole32!CoTaskMemFree` at `0x1800340cd`
- `ole32!CoTaskMemFree` at `0x1800340dc`
- `ole32!CoTaskMemFree` at `0x1800340eb`
- `ole32!CoTaskMemFree` at `0x1800340fa`
- `ole32!CoTaskMemFree` at `0x180034109`
- `ole32!CoTaskMemFree` at `0x180034118`
- `ole32!CoTaskMemFree` at `0x180034127`
- `ole32!CoTaskMemFree` at `0x180034130`

## pseudocode

```c
void __fastcall ShieldProvider::FreeMpThreatLocalizedInfo(ShieldProvider *this, struct tagMPTHREAT_LOCALIZED_INFO *a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx

  if ( this )
  {
    v3 = (void *)*((_QWORD *)this + 1);
    if ( v3 )
      CoTaskMemFree(v3);
    v4 = (void *)*((_QWORD *)this + 2);
    if ( v4 )
      CoTaskMemFree(v4);
    v5 = (void *)*((_QWORD *)this + 3);
    if ( v5 )
      CoTaskMemFree(v5);
    v6 = (void *)*((_QWORD *)this + 4);
    if ( v6 )
      CoTaskMemFree(v6);
    v7 = (void *)*((_QWORD *)this + 5);
    if ( v7 )
      CoTaskMemFree(v7);
    v8 = (void *)*((_QWORD *)this + 6);
    if ( v8 )
      CoTaskMemFree(v8);
    v9 = (void *)*((_QWORD *)this + 7);
    if ( v9 )
      CoTaskMemFree(v9);
    v10 = (void *)*((_QWORD *)this + 8);
    if ( v10 )
      CoTaskMemFree(v10);
    CoTaskMemFree(this);
  }
}

```

## disassembly

```asm
0x1800340a4  test    rcx, rcx
0x1800340a7  jz      locret_18003413B
0x1800340ad  push    rbx
0x1800340ae  sub     rsp, 20h
0x1800340b2  mov     rbx, rcx
0x1800340b5  mov     rcx, [rcx+8]; pv
0x1800340b9  test    rcx, rcx
0x1800340bc  jz      short loc_1800340C4
0x1800340be  call    cs:__imp_CoTaskMemFree
0x1800340c4  mov     rcx, [rbx+10h]; pv
0x1800340c8  test    rcx, rcx
0x1800340cb  jz      short loc_1800340D3
0x1800340cd  call    cs:__imp_CoTaskMemFree
0x1800340d3  mov     rcx, [rbx+18h]; pv
0x1800340d7  test    rcx, rcx
0x1800340da  jz      short loc_1800340E2
0x1800340dc  call    cs:__imp_CoTaskMemFree
0x1800340e2  mov     rcx, [rbx+20h]; pv
0x1800340e6  test    rcx, rcx
0x1800340e9  jz      short loc_1800340F1
0x1800340eb  call    cs:__imp_CoTaskMemFree
0x1800340f1  mov     rcx, [rbx+28h]; pv
0x1800340f5  test    rcx, rcx
0x1800340f8  jz      short loc_180034100
0x1800340fa  call    cs:__imp_CoTaskMemFree
0x180034100  mov     rcx, [rbx+30h]; pv
0x180034104  test    rcx, rcx
0x180034107  jz      short loc_18003410F
0x180034109  call    cs:__imp_CoTaskMemFree
0x18003410f  mov     rcx, [rbx+38h]; pv
0x180034113  test    rcx, rcx
0x180034116  jz      short loc_18003411E
0x180034118  call    cs:__imp_CoTaskMemFree
0x18003411e  mov     rcx, [rbx+40h]; pv
0x180034122  test    rcx, rcx
0x180034125  jz      short loc_18003412D
0x180034127  call    cs:__imp_CoTaskMemFree
0x18003412d  mov     rcx, rbx; pv
0x180034130  call    cs:__imp_CoTaskMemFree
0x180034136  add     rsp, 20h
0x18003413a  pop     rbx
0x18003413b  retn
```
