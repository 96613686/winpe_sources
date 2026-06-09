# ShieldProvider::FreeFirewallProfileStatusEx(tagFIREWALL_PROFILE_STATUS_EX *)

- ea: `0x1800489d8`
- end: `0x180048a82`
- name: `?FreeFirewallProfileStatusEx@ShieldProvider@@YAXPEAUtagFIREWALL_PROFILE_STATUS_EX@@@Z`
- size: `170`
- prototype: `void __fastcall(ShieldProvider *__hidden this, struct tagFIREWALL_PROFILE_STATUS_EX *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180049ee4`
- `0x18004a670`

## callees

- `0x1800489d8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800489f2`
- `ole32!CoTaskMemFree` at `0x180048a09`
- `ole32!CoTaskMemFree` at `0x180048a20`
- `ole32!CoTaskMemFree` at `0x180048a37`
- `ole32!CoTaskMemFree` at `0x180048a4e`
- `ole32!CoTaskMemFree` at `0x180048a65`
- `ole32!CoTaskMemFree` at `0x180048a76`
- `ole32!CoTaskMemFree` at `0x1800489f2`
- `ole32!CoTaskMemFree` at `0x180048a09`
- `ole32!CoTaskMemFree` at `0x180048a20`
- `ole32!CoTaskMemFree` at `0x180048a37`
- `ole32!CoTaskMemFree` at `0x180048a4e`
- `ole32!CoTaskMemFree` at `0x180048a65`
- `ole32!CoTaskMemFree` at `0x180048a76`

## pseudocode

```c
void __fastcall ShieldProvider::FreeFirewallProfileStatusEx(
        ShieldProvider *this,
        struct tagFIREWALL_PROFILE_STATUS_EX *a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( this )
  {
    v3 = (void *)*((_QWORD *)this + 1);
    if ( v3 )
    {
      CoTaskMemFree(v3);
      *((_QWORD *)this + 1) = 0;
    }
    v4 = (void *)*((_QWORD *)this + 2);
    if ( v4 )
    {
      CoTaskMemFree(v4);
      *((_QWORD *)this + 2) = 0;
    }
    v5 = (void *)*((_QWORD *)this + 7);
    if ( v5 )
    {
      CoTaskMemFree(v5);
      *((_QWORD *)this + 7) = 0;
    }
    v6 = (void *)*((_QWORD *)this + 8);
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *((_QWORD *)this + 8) = 0;
    }
    v7 = (void *)*((_QWORD *)this + 4);
    if ( v7 )
    {
      CoTaskMemFree(v7);
      *((_QWORD *)this + 4) = 0;
    }
    v8 = (void *)*((_QWORD *)this + 5);
    if ( v8 )
    {
      CoTaskMemFree(v8);
      *((_QWORD *)this + 5) = 0;
    }
    CoTaskMemFree(this);
  }
}

```

## disassembly

```asm
0x1800489d8  test    rcx, rcx
0x1800489db  jz      locret_180048A81
0x1800489e1  push    rbx
0x1800489e2  sub     rsp, 20h
0x1800489e6  mov     rbx, rcx
0x1800489e9  mov     rcx, [rcx+8]; pv
0x1800489ed  test    rcx, rcx
0x1800489f0  jz      short loc_180048A00
0x1800489f2  call    cs:__imp_CoTaskMemFree
0x1800489f8  mov     qword ptr [rbx+8], 0
0x180048a00  mov     rcx, [rbx+10h]; pv
0x180048a04  test    rcx, rcx
0x180048a07  jz      short loc_180048A17
0x180048a09  call    cs:__imp_CoTaskMemFree
0x180048a0f  mov     qword ptr [rbx+10h], 0
0x180048a17  mov     rcx, [rbx+38h]; pv
0x180048a1b  test    rcx, rcx
0x180048a1e  jz      short loc_180048A2E
0x180048a20  call    cs:__imp_CoTaskMemFree
0x180048a26  mov     qword ptr [rbx+38h], 0
0x180048a2e  mov     rcx, [rbx+40h]; pv
0x180048a32  test    rcx, rcx
0x180048a35  jz      short loc_180048A45
0x180048a37  call    cs:__imp_CoTaskMemFree
0x180048a3d  mov     qword ptr [rbx+40h], 0
0x180048a45  mov     rcx, [rbx+20h]; pv
0x180048a49  test    rcx, rcx
0x180048a4c  jz      short loc_180048A5C
0x180048a4e  call    cs:__imp_CoTaskMemFree
0x180048a54  mov     qword ptr [rbx+20h], 0
0x180048a5c  mov     rcx, [rbx+28h]; pv
0x180048a60  test    rcx, rcx
0x180048a63  jz      short loc_180048A73
0x180048a65  call    cs:__imp_CoTaskMemFree
0x180048a6b  mov     qword ptr [rbx+28h], 0
0x180048a73  mov     rcx, rbx; pv
0x180048a76  call    cs:__imp_CoTaskMemFree
0x180048a7c  add     rsp, 20h
0x180048a80  pop     rbx
0x180048a81  retn
```
