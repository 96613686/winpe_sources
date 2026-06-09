# ShieldProvider::FreeMpThreatInfo(tagMPTHREAT_INFO *)

- ea: `0x18002a034`
- end: `0x18002a160`
- name: `?FreeMpThreatInfo@ShieldProvider@@YAXPEAUtagMPTHREAT_INFO@@@Z`
- size: `300`
- prototype: `void __fastcall(ShieldProvider *__hidden this, struct tagMPTHREAT_INFO *)`
- caller_count: `10`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002a25c`
- `0x18002c488`
- `0x180030440`
- `0x1800315ac`
- `0x180031a2c`
- `0x180031bf0`
- `0x180034434`
- `0x18003522c`
- `0x180035fac`
- `0x180036250`

## callees

- `0x180029fe4`
- `0x18002a034`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002a053`
- `ole32!CoTaskMemFree` at `0x18002a065`
- `ole32!CoTaskMemFree` at `0x18002a077`
- `ole32!CoTaskMemFree` at `0x18002a089`
- `ole32!CoTaskMemFree` at `0x18002a0b5`
- `ole32!CoTaskMemFree` at `0x18002a0e0`
- `ole32!CoTaskMemFree` at `0x18002a0ef`
- `ole32!CoTaskMemFree` at `0x18002a0fe`
- `ole32!CoTaskMemFree` at `0x18002a11f`
- `ole32!CoTaskMemFree` at `0x18002a12e`
- `ole32!CoTaskMemFree` at `0x18002a13d`
- `ole32!CoTaskMemFree` at `0x18002a146`
- `ole32!CoTaskMemFree` at `0x18002a14f`
- `ole32!CoTaskMemFree` at `0x18002a053`
- `ole32!CoTaskMemFree` at `0x18002a065`
- `ole32!CoTaskMemFree` at `0x18002a077`
- `ole32!CoTaskMemFree` at `0x18002a089`
- `ole32!CoTaskMemFree` at `0x18002a0b5`
- `ole32!CoTaskMemFree` at `0x18002a0e0`
- `ole32!CoTaskMemFree` at `0x18002a0ef`
- `ole32!CoTaskMemFree` at `0x18002a0fe`
- `ole32!CoTaskMemFree` at `0x18002a11f`
- `ole32!CoTaskMemFree` at `0x18002a12e`
- `ole32!CoTaskMemFree` at `0x18002a13d`
- `ole32!CoTaskMemFree` at `0x18002a146`
- `ole32!CoTaskMemFree` at `0x18002a14f`

## pseudocode

```c
void __fastcall ShieldProvider::FreeMpThreatInfo(ShieldProvider *this, struct tagMPTHREAT_INFO *a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 i; // rdi
  __int64 v8; // rdi
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx

  if ( this )
  {
    v3 = (void *)*((_QWORD *)this + 3);
    if ( v3 )
      CoTaskMemFree(v3);
    v4 = (void *)*((_QWORD *)this + 19);
    if ( v4 )
      CoTaskMemFree(v4);
    v5 = (void *)*((_QWORD *)this + 21);
    if ( v5 )
      CoTaskMemFree(v5);
    v6 = (void *)*((_QWORD *)this + 28);
    if ( v6 )
      CoTaskMemFree(v6);
    if ( *((_QWORD *)this + 11) )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 21); i = (unsigned int)(i + 1) )
        ShieldProvider::FreeMpResourceInfo(*(ShieldProvider **)(*((_QWORD *)this + 11) + 8 * i), a2);
      CoTaskMemFree(*((LPVOID *)this + 11));
    }
    if ( *((_DWORD *)this + 8) == 1 )
    {
      v8 = *((_QWORD *)this + 17);
      if ( v8 )
      {
        v12 = *(void **)(v8 + 40);
        if ( v12 )
          CoTaskMemFree(v12);
        v13 = *(void **)(v8 + 48);
        if ( v13 )
          CoTaskMemFree(v13);
        v11 = *(void **)(v8 + 56);
        goto LABEL_30;
      }
    }
    else if ( *((_DWORD *)this + 8) == 4 )
    {
      v8 = *((_QWORD *)this + 17);
      if ( v8 )
      {
        if ( *(_QWORD *)v8 )
          CoTaskMemFree(*(LPVOID *)v8);
        v9 = *(void **)(v8 + 8);
        if ( v9 )
          CoTaskMemFree(v9);
        v10 = *(void **)(v8 + 24);
        if ( v10 )
          CoTaskMemFree(v10);
        v11 = *(void **)(v8 + 32);
LABEL_30:
        if ( v11 )
          CoTaskMemFree(v11);
        CoTaskMemFree((LPVOID)v8);
      }
    }
    CoTaskMemFree(this);
  }
}

```

## disassembly

```asm
0x18002a034  test    rcx, rcx
0x18002a037  jz      locret_18002A15F
0x18002a03d  mov     [rsp+arg_0], rbx
0x18002a042  push    rdi
0x18002a043  sub     rsp, 20h
0x18002a047  mov     rbx, rcx
0x18002a04a  mov     rcx, [rcx+18h]; pv
0x18002a04e  test    rcx, rcx
0x18002a051  jz      short loc_18002A059
0x18002a053  call    cs:__imp_CoTaskMemFree
0x18002a059  mov     rcx, [rbx+98h]; pv
0x18002a060  test    rcx, rcx
0x18002a063  jz      short loc_18002A06B
0x18002a065  call    cs:__imp_CoTaskMemFree
0x18002a06b  mov     rcx, [rbx+0A8h]; pv
0x18002a072  test    rcx, rcx
0x18002a075  jz      short loc_18002A07D
0x18002a077  call    cs:__imp_CoTaskMemFree
0x18002a07d  mov     rcx, [rbx+0E0h]; pv
0x18002a084  test    rcx, rcx
0x18002a087  jz      short loc_18002A08F
0x18002a089  call    cs:__imp_CoTaskMemFree
0x18002a08f  cmp     qword ptr [rbx+58h], 0
0x18002a094  jz      short loc_18002A0BB
0x18002a096  xor     edi, edi
0x18002a098  cmp     [rbx+54h], edi
0x18002a09b  jbe     short loc_18002A0B1
0x18002a09d  mov     rcx, [rbx+58h]
0x18002a0a1  mov     rcx, [rcx+rdi*8]; this
0x18002a0a5  call    ?FreeMpResourceInfo@ShieldProvider@@YAXPEAUtagMPRESOURCE_INFO@@@Z; ShieldProvider::FreeMpResourceInfo(tagMPRESOURCE_INFO *)
0x18002a0aa  inc     edi
0x18002a0ac  cmp     edi, [rbx+54h]
0x18002a0af  jb      short loc_18002A09D
0x18002a0b1  mov     rcx, [rbx+58h]; pv
0x18002a0b5  call    cs:__imp_CoTaskMemFree
0x18002a0bb  mov     ecx, [rbx+20h]
0x18002a0be  sub     ecx, 1
0x18002a0c1  jz      short loc_18002A10A
0x18002a0c3  cmp     ecx, 3
0x18002a0c6  jnz     loc_18002A14C
0x18002a0cc  mov     rdi, [rbx+88h]
0x18002a0d3  test    rdi, rdi
0x18002a0d6  jz      short loc_18002A14C
0x18002a0d8  mov     rcx, [rdi]; pv
0x18002a0db  test    rcx, rcx
0x18002a0de  jz      short loc_18002A0E6
0x18002a0e0  call    cs:__imp_CoTaskMemFree
0x18002a0e6  mov     rcx, [rdi+8]; pv
0x18002a0ea  test    rcx, rcx
0x18002a0ed  jz      short loc_18002A0F5
0x18002a0ef  call    cs:__imp_CoTaskMemFree
0x18002a0f5  mov     rcx, [rdi+18h]; pv
0x18002a0f9  test    rcx, rcx
0x18002a0fc  jz      short loc_18002A104
0x18002a0fe  call    cs:__imp_CoTaskMemFree
0x18002a104  mov     rcx, [rdi+20h]
0x18002a108  jmp     short loc_18002A138
0x18002a10a  mov     rdi, [rbx+88h]
0x18002a111  test    rdi, rdi
0x18002a114  jz      short loc_18002A14C
0x18002a116  mov     rcx, [rdi+28h]; pv
0x18002a11a  test    rcx, rcx
0x18002a11d  jz      short loc_18002A125
0x18002a11f  call    cs:__imp_CoTaskMemFree
0x18002a125  mov     rcx, [rdi+30h]; pv
0x18002a129  test    rcx, rcx
0x18002a12c  jz      short loc_18002A134
0x18002a12e  call    cs:__imp_CoTaskMemFree
0x18002a134  mov     rcx, [rdi+38h]; pv
0x18002a138  test    rcx, rcx
0x18002a13b  jz      short loc_18002A143
0x18002a13d  call    cs:__imp_CoTaskMemFree
0x18002a143  mov     rcx, rdi; pv
0x18002a146  call    cs:__imp_CoTaskMemFree
0x18002a14c  mov     rcx, rbx; pv
0x18002a14f  call    cs:__imp_CoTaskMemFree
0x18002a155  mov     rbx, [rsp+28h+arg_0]
0x18002a15a  add     rsp, 20h
0x18002a15e  pop     rdi
0x18002a15f  retn
```
