# ShieldProvider::ThreatProtectionShield::DoesActiveProductSupportLaunch(int *)

- ea: `0x180038080`
- end: `0x180038152`
- name: `?DoesActiveProductSupportLaunch@ThreatProtectionShield@ShieldProvider@@UEAAJPEAH@Z`
- size: `210`
- prototype: `__int64 __fastcall(ShieldProvider::ThreatProtectionShield *__hidden this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000d7fc`
- `0x180038080`
- `0x1800e7010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800380f2`
- `ole32!CoTaskMemFree` at `0x180038101`
- `ole32!CoTaskMemFree` at `0x18003810a`
- `ole32!CoTaskMemFree` at `0x180038127`
- `ole32!CoTaskMemFree` at `0x180038136`
- `ole32!CoTaskMemFree` at `0x18003813f`
- `ole32!CoTaskMemFree` at `0x1800380f2`
- `ole32!CoTaskMemFree` at `0x180038101`
- `ole32!CoTaskMemFree` at `0x18003810a`
- `ole32!CoTaskMemFree` at `0x180038127`
- `ole32!CoTaskMemFree` at `0x180038136`
- `ole32!CoTaskMemFree` at `0x18003813f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShieldProvider::ThreatProtectionShield::DoesActiveProductSupportLaunch(
        ShieldProvider::ThreatProtectionShield *this,
        int *a2)
{
  int v2; // edi
  _QWORD *v3; // rbx
  void *v4; // rcx
  void *v5; // rcx
  _QWORD *v7; // rbx
  void *v8; // rcx
  void *v9; // rcx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  pv = 0;
  v2 = (*(__int64 (__fastcall **)(ShieldProvider::ThreatProtectionShield *, LPVOID *, int *))(*(_QWORD *)this + 40LL))(
         this,
         &pv,
         a2);
  if ( v2 >= 0 )
  {
    v7 = pv;
    if ( pv )
    {
      v8 = (void *)*((_QWORD *)pv + 1);
      if ( v8 )
        CoTaskMemFree(v8);
      v9 = (void *)v7[2];
      if ( v9 )
        CoTaskMemFree(v9);
      CoTaskMemFree(v7);
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_4608de75ba8c308c3f60bea69d382694_Traceguids,
        (unsigned int)v2);
    v3 = pv;
    if ( pv )
    {
      v4 = (void *)*((_QWORD *)pv + 1);
      if ( v4 )
        CoTaskMemFree(v4);
      v5 = (void *)v3[2];
      if ( v5 )
        CoTaskMemFree(v5);
      CoTaskMemFree(v3);
    }
    return (unsigned int)v2;
  }
}

```

## disassembly

```asm
0x180038080  mov     [rsp+arg_8], rbx
0x180038085  push    rdi
0x180038086  sub     rsp, 20h
0x18003808a  mov     [rsp+28h+pv], 0
0x180038093  mov     rax, [rcx]
0x180038096  mov     r8, rdx
0x180038099  lea     rdx, [rsp+28h+pv]
0x18003809e  mov     rax, [rax+28h]
0x1800380a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380a7  mov     edi, eax
0x1800380a9  test    eax, eax
0x1800380ab  jns     short loc_180038114
0x1800380ad  lea     rax, WPP_GLOBAL_Control
0x1800380b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380bb  cmp     rcx, rax
0x1800380be  jz      short loc_1800380DF
0x1800380c0  test    byte ptr [rcx+1Ch], 1
0x1800380c4  jz      short loc_1800380DF
0x1800380c6  mov     edx, 0Fh
0x1800380cb  mov     r9d, edi
0x1800380ce  lea     r8, WPP_4608de75ba8c308c3f60bea69d382694_Traceguids
0x1800380d5  mov     rcx, [rcx+10h]
0x1800380d9  call    WPP_SF_d
0x1800380de  nop
0x1800380df  mov     rbx, [rsp+28h+pv]
0x1800380e4  test    rbx, rbx
0x1800380e7  jz      short loc_180038110
0x1800380e9  mov     rcx, [rbx+8]; pv
0x1800380ed  test    rcx, rcx
0x1800380f0  jz      short loc_1800380F8
0x1800380f2  call    cs:__imp_CoTaskMemFree
0x1800380f8  mov     rcx, [rbx+10h]; pv
0x1800380fc  test    rcx, rcx
0x1800380ff  jz      short loc_180038107
0x180038101  call    cs:__imp_CoTaskMemFree
0x180038107  mov     rcx, rbx; pv
0x18003810a  call    cs:__imp_CoTaskMemFree
0x180038110  mov     eax, edi
0x180038112  jmp     short loc_180038147
0x180038114  mov     rbx, [rsp+28h+pv]
0x180038119  test    rbx, rbx
0x18003811c  jz      short loc_180038145
0x18003811e  mov     rcx, [rbx+8]; pv
0x180038122  test    rcx, rcx
0x180038125  jz      short loc_18003812D
0x180038127  call    cs:__imp_CoTaskMemFree
0x18003812d  mov     rcx, [rbx+10h]; pv
0x180038131  test    rcx, rcx
0x180038134  jz      short loc_18003813C
0x180038136  call    cs:__imp_CoTaskMemFree
0x18003813c  mov     rcx, rbx; pv
0x18003813f  call    cs:__imp_CoTaskMemFree
0x180038145  xor     eax, eax
0x180038147  mov     rbx, [rsp+28h+arg_8]
0x18003814c  add     rsp, 20h
0x180038150  pop     rdi
0x180038151  retn
```
