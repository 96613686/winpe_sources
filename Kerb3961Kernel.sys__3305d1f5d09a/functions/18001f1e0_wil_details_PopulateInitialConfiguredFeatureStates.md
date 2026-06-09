# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x18001f1e0`
- end: `0x18001f35f`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001f078`

## callees

- `0x180012200`
- `0x18001f1e0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18001f25c`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18001f25c`

## pseudocode

```c
void wil_details_PopulateInitialConfiguredFeatureStates()
{
  _QWORD *i; // rbx
  int v1; // eax
  __int64 *v2; // rcx
  _QWORD *v3; // rcx
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+28h] [rbp-20h] BYREF
  int v6; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; ; ++i )
  {
    if ( i >= wil_details_featureDescriptors_a )
      return;
    if ( *i )
      break;
  }
LABEL_20:
  if ( !i )
    return;
  v5 = 0;
  v6 = 0;
  v4 = 0;
  if ( *((_BYTE *)i + 29) || *((_BYTE *)i + 30) )
    goto LABEL_14;
  v1 = ((__int64 (__fastcall *)(_QWORD, bool, __int64 *, __int64 *))RtlQueryFeatureConfiguration)(
         *((unsigned int *)i + 6),
         (unsigned __int8)(*((_BYTE *)i + 28) - 2) > 1u,
         &v4,
         &v5);
  if ( v1 != -2147483614 )
  {
    if ( v1 != -1073741275 )
    {
      if ( !v1 )
      {
        v4 = (8 * (BYTE4(v5) & 0xB0 | (4 * (BYTE4(v5) & 0x40u)))) | 0x206LL;
        goto LABEL_15;
      }
      if ( v1 == 279 )
      {
        v4 = (8 * (BYTE4(v5) & 0x80u)) | 0x206LL;
        goto LABEL_15;
      }
    }
LABEL_14:
    v4 = 518;
LABEL_15:
    v2 = (__int64 *)*i;
    i += 7;
    *v2 = v4;
    while ( i < wil_details_featureDescriptors_a )
    {
      if ( *i )
        goto LABEL_20;
      ++i;
    }
    return;
  }
  v4 = 518;
LABEL_23:
  v3 = (_QWORD *)*i;
  i += 7;
  *v3 = 518;
  while ( i < wil_details_featureDescriptors_a )
  {
    if ( *i )
    {
      if ( i )
        goto LABEL_23;
      return;
    }
    ++i;
  }
}

```

## disassembly

```asm
0x18001f1e0  mov     [rsp+arg_0], rbx
0x18001f1e5  push    rsi
0x18001f1e6  sub     rsp, 40h
0x18001f1ea  mov     rax, cs:__security_cookie
0x18001f1f1  xor     rax, rsp
0x18001f1f4  mov     [rsp+48h+var_10], rax
0x18001f1f9  lea     rbx, wil_details_featureDescriptors_a
0x18001f200  lea     rsi, wil_details_featureDescriptors_a
0x18001f207  jmp     short loc_18001F217
0x18001f209  cmp     qword ptr [rbx], 0
0x18001f20d  jnz     loc_18001F303
0x18001f213  add     rbx, 8
0x18001f217  cmp     rbx, rsi
0x18001f21a  jb      short loc_18001F209
0x18001f21c  jmp     loc_18001F346
0x18001f221  xor     eax, eax
0x18001f223  mov     [rsp+48h+var_20], rax
0x18001f228  mov     [rsp+48h+var_18], eax
0x18001f22c  mov     [rsp+48h+var_28], rax
0x18001f231  cmp     [rbx+1Dh], al
0x18001f234  jnz     loc_18001F2D0
0x18001f23a  cmp     [rbx+1Eh], al
0x18001f23d  jnz     loc_18001F2D0
0x18001f243  mov     al, [rbx+1Ch]
0x18001f246  lea     r9, [rsp+48h+var_20]
0x18001f24b  mov     ecx, [rbx+18h]
0x18001f24e  lea     r8, [rsp+48h+var_28]
0x18001f253  xor     edx, edx
0x18001f255  sub     al, 2
0x18001f257  cmp     al, 1
0x18001f259  setnbe  dl
0x18001f25c  call    cs:__imp_RtlQueryFeatureConfiguration
0x18001f263  nop     dword ptr [rax+rax+00h]
0x18001f268  cmp     eax, 80000022h
0x18001f26d  jz      loc_18001F30E
0x18001f273  cmp     eax, 0C0000225h
0x18001f278  jz      short loc_18001F2D0
0x18001f27a  test    eax, eax
0x18001f27c  jz      short loc_18001F2A5
0x18001f27e  cmp     eax, 117h
0x18001f283  jnz     short loc_18001F2D0
0x18001f285  mov     eax, dword ptr [rsp+48h+var_20+4]
0x18001f289  and     eax, 80h
0x18001f28e  mov     [rsp+48h+var_28], 0
0x18001f297  shl     eax, 3
0x18001f29a  or      eax, 206h
0x18001f29f  mov     dword ptr [rsp+48h+var_28], eax
0x18001f2a3  jmp     short loc_18001F2E1
0x18001f2a5  mov     eax, dword ptr [rsp+48h+var_20+4]
0x18001f2a9  mov     ecx, eax
0x18001f2ab  and     ecx, 40h
0x18001f2ae  mov     [rsp+48h+var_28], 0
0x18001f2b7  shl     ecx, 2
0x18001f2ba  and     eax, 0B0h
0x18001f2bf  or      ecx, eax
0x18001f2c1  shl     ecx, 3
0x18001f2c4  or      ecx, 206h
0x18001f2ca  mov     dword ptr [rsp+48h+var_28], ecx
0x18001f2ce  jmp     short loc_18001F2E1
0x18001f2d0  mov     [rsp+48h+var_28], 0
0x18001f2d9  mov     dword ptr [rsp+48h+var_28], 206h
0x18001f2e1  mov     rcx, [rbx]
0x18001f2e4  add     rbx, 38h ; '8'
0x18001f2e8  mov     rax, [rsp+48h+var_28]
0x18001f2ed  mov     [rcx], rax
0x18001f2f0  jmp     short loc_18001F2FC
0x18001f2f2  cmp     qword ptr [rbx], 0
0x18001f2f6  jnz     short loc_18001F303
0x18001f2f8  add     rbx, 8
0x18001f2fc  cmp     rbx, rsi
0x18001f2ff  jb      short loc_18001F2F2
0x18001f301  jmp     short loc_18001F346
0x18001f303  test    rbx, rbx
0x18001f306  jnz     loc_18001F221
0x18001f30c  jmp     short loc_18001F346
0x18001f30e  mov     [rsp+48h+var_28], 0
0x18001f317  mov     dword ptr [rsp+48h+var_28], 206h
0x18001f31f  mov     rax, [rsp+48h+var_28]
0x18001f324  mov     rcx, [rbx]
0x18001f327  add     rbx, 38h ; '8'
0x18001f32b  mov     [rcx], rax
0x18001f32e  jmp     short loc_18001F33A
0x18001f330  cmp     qword ptr [rbx], 0
0x18001f334  jnz     short loc_18001F341
0x18001f336  add     rbx, 8
0x18001f33a  cmp     rbx, rsi
0x18001f33d  jb      short loc_18001F330
0x18001f33f  jmp     short loc_18001F346
0x18001f341  test    rbx, rbx
0x18001f344  jnz     short loc_18001F324
0x18001f346  mov     rcx, [rsp+48h+var_10]
0x18001f34b  xor     rcx, rsp; StackCookie
0x18001f34e  call    __security_check_cookie
0x18001f353  mov     rbx, [rsp+48h+arg_0]
0x18001f358  add     rsp, 40h
0x18001f35c  pop     rsi
0x18001f35d  retn
```
