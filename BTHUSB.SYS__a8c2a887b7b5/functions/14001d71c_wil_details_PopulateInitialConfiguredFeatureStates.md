# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14001d71c`
- end: `0x14001d89b`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001d5b4`

## callees

- `0x14000ddc0`
- `0x14001d71c`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001d798`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001d798`

## pseudocode

```c
void wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 *i; // rbx
  int v1; // eax
  _QWORD *v2; // rcx
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
    v2 = (_QWORD *)*i;
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
0x14001d71c  mov     [rsp+arg_0], rbx
0x14001d721  push    rsi
0x14001d722  sub     rsp, 40h
0x14001d726  mov     rax, cs:__security_cookie
0x14001d72d  xor     rax, rsp
0x14001d730  mov     [rsp+48h+var_10], rax
0x14001d735  lea     rbx, wil_details_featureDescriptors_a
0x14001d73c  lea     rsi, wil_details_featureDescriptors_a
0x14001d743  jmp     short loc_14001D753
0x14001d745  cmp     qword ptr [rbx], 0
0x14001d749  jnz     loc_14001D83F
0x14001d74f  add     rbx, 8
0x14001d753  cmp     rbx, rsi
0x14001d756  jb      short loc_14001D745
0x14001d758  jmp     loc_14001D882
0x14001d75d  xor     eax, eax
0x14001d75f  mov     [rsp+48h+var_20], rax
0x14001d764  mov     [rsp+48h+var_18], eax
0x14001d768  mov     [rsp+48h+var_28], rax
0x14001d76d  cmp     [rbx+1Dh], al
0x14001d770  jnz     loc_14001D80C
0x14001d776  cmp     [rbx+1Eh], al
0x14001d779  jnz     loc_14001D80C
0x14001d77f  mov     al, [rbx+1Ch]
0x14001d782  lea     r9, [rsp+48h+var_20]
0x14001d787  mov     ecx, [rbx+18h]
0x14001d78a  lea     r8, [rsp+48h+var_28]
0x14001d78f  xor     edx, edx
0x14001d791  sub     al, 2
0x14001d793  cmp     al, 1
0x14001d795  setnbe  dl
0x14001d798  call    cs:__imp_RtlQueryFeatureConfiguration
0x14001d79f  nop     dword ptr [rax+rax+00h]
0x14001d7a4  cmp     eax, 80000022h
0x14001d7a9  jz      loc_14001D84A
0x14001d7af  cmp     eax, 0C0000225h
0x14001d7b4  jz      short loc_14001D80C
0x14001d7b6  test    eax, eax
0x14001d7b8  jz      short loc_14001D7E1
0x14001d7ba  cmp     eax, 117h
0x14001d7bf  jnz     short loc_14001D80C
0x14001d7c1  mov     eax, dword ptr [rsp+48h+var_20+4]
0x14001d7c5  and     eax, 80h
0x14001d7ca  mov     [rsp+48h+var_28], 0
0x14001d7d3  shl     eax, 3
0x14001d7d6  or      eax, 206h
0x14001d7db  mov     dword ptr [rsp+48h+var_28], eax
0x14001d7df  jmp     short loc_14001D81D
0x14001d7e1  mov     eax, dword ptr [rsp+48h+var_20+4]
0x14001d7e5  mov     ecx, eax
0x14001d7e7  and     ecx, 40h
0x14001d7ea  mov     [rsp+48h+var_28], 0
0x14001d7f3  shl     ecx, 2
0x14001d7f6  and     eax, 0B0h
0x14001d7fb  or      ecx, eax
0x14001d7fd  shl     ecx, 3
0x14001d800  or      ecx, 206h
0x14001d806  mov     dword ptr [rsp+48h+var_28], ecx
0x14001d80a  jmp     short loc_14001D81D
0x14001d80c  mov     [rsp+48h+var_28], 0
0x14001d815  mov     dword ptr [rsp+48h+var_28], 206h
0x14001d81d  mov     rcx, [rbx]
0x14001d820  add     rbx, 38h ; '8'
0x14001d824  mov     rax, [rsp+48h+var_28]
0x14001d829  mov     [rcx], rax
0x14001d82c  jmp     short loc_14001D838
0x14001d82e  cmp     qword ptr [rbx], 0
0x14001d832  jnz     short loc_14001D83F
0x14001d834  add     rbx, 8
0x14001d838  cmp     rbx, rsi
0x14001d83b  jb      short loc_14001D82E
0x14001d83d  jmp     short loc_14001D882
0x14001d83f  test    rbx, rbx
0x14001d842  jnz     loc_14001D75D
0x14001d848  jmp     short loc_14001D882
0x14001d84a  mov     [rsp+48h+var_28], 0
0x14001d853  mov     dword ptr [rsp+48h+var_28], 206h
0x14001d85b  mov     rax, [rsp+48h+var_28]
0x14001d860  mov     rcx, [rbx]
0x14001d863  add     rbx, 38h ; '8'
0x14001d867  mov     [rcx], rax
0x14001d86a  jmp     short loc_14001D876
0x14001d86c  cmp     qword ptr [rbx], 0
0x14001d870  jnz     short loc_14001D87D
0x14001d872  add     rbx, 8
0x14001d876  cmp     rbx, rsi
0x14001d879  jb      short loc_14001D86C
0x14001d87b  jmp     short loc_14001D882
0x14001d87d  test    rbx, rbx
0x14001d880  jnz     short loc_14001D860
0x14001d882  mov     rcx, [rsp+48h+var_10]
0x14001d887  xor     rcx, rsp; StackCookie
0x14001d88a  call    __security_check_cookie
0x14001d88f  mov     rbx, [rsp+48h+arg_0]
0x14001d894  add     rsp, 40h
0x14001d898  pop     rsi
0x14001d899  retn
```
