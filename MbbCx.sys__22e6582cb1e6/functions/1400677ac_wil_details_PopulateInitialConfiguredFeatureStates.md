# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x1400677ac`
- end: `0x14006792b`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140067644`

## callees

- `0x140047e50`
- `0x1400677ac`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140067828`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140067828`

## pseudocode

```c
void wil_details_PopulateInitialConfiguredFeatureStates()
{
  int **i; // rbx
  int v1; // eax
  _QWORD *v2; // rcx
  int *v3; // rcx
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+28h] [rbp-20h] BYREF
  int v6; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; ; ++i )
  {
    if ( i >= (int **)wil_details_featureDescriptors_z )
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
    v2 = *i;
    i += 7;
    *v2 = v4;
    while ( i < (int **)wil_details_featureDescriptors_z )
    {
      if ( *i )
        goto LABEL_20;
      ++i;
    }
    return;
  }
  v4 = 518;
LABEL_23:
  v3 = *i;
  i += 7;
  *(_QWORD *)v3 = 518;
  while ( i < (int **)wil_details_featureDescriptors_z )
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
0x1400677ac  mov     [rsp+arg_0], rbx
0x1400677b1  push    rsi
0x1400677b2  sub     rsp, 40h
0x1400677b6  mov     rax, cs:__security_cookie
0x1400677bd  xor     rax, rsp
0x1400677c0  mov     [rsp+48h+var_10], rax
0x1400677c5  lea     rbx, wil_details_featureDescriptors_a
0x1400677cc  lea     rsi, wil_details_featureDescriptors_z
0x1400677d3  jmp     short loc_1400677E3
0x1400677d5  cmp     qword ptr [rbx], 0
0x1400677d9  jnz     loc_1400678CF
0x1400677df  add     rbx, 8
0x1400677e3  cmp     rbx, rsi
0x1400677e6  jb      short loc_1400677D5
0x1400677e8  jmp     loc_140067912
0x1400677ed  xor     eax, eax
0x1400677ef  mov     [rsp+48h+var_20], rax
0x1400677f4  mov     [rsp+48h+var_18], eax
0x1400677f8  mov     [rsp+48h+var_28], rax
0x1400677fd  cmp     [rbx+1Dh], al
0x140067800  jnz     loc_14006789C
0x140067806  cmp     [rbx+1Eh], al
0x140067809  jnz     loc_14006789C
0x14006780f  mov     al, [rbx+1Ch]
0x140067812  lea     r9, [rsp+48h+var_20]
0x140067817  mov     ecx, [rbx+18h]
0x14006781a  lea     r8, [rsp+48h+var_28]
0x14006781f  xor     edx, edx
0x140067821  sub     al, 2
0x140067823  cmp     al, 1
0x140067825  setnbe  dl
0x140067828  call    cs:__imp_RtlQueryFeatureConfiguration
0x14006782f  nop     dword ptr [rax+rax+00h]
0x140067834  cmp     eax, 80000022h
0x140067839  jz      loc_1400678DA
0x14006783f  cmp     eax, 0C0000225h
0x140067844  jz      short loc_14006789C
0x140067846  test    eax, eax
0x140067848  jz      short loc_140067871
0x14006784a  cmp     eax, 117h
0x14006784f  jnz     short loc_14006789C
0x140067851  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140067855  and     eax, 80h
0x14006785a  mov     [rsp+48h+var_28], 0
0x140067863  shl     eax, 3
0x140067866  or      eax, 206h
0x14006786b  mov     dword ptr [rsp+48h+var_28], eax
0x14006786f  jmp     short loc_1400678AD
0x140067871  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140067875  mov     ecx, eax
0x140067877  and     ecx, 40h
0x14006787a  mov     [rsp+48h+var_28], 0
0x140067883  shl     ecx, 2
0x140067886  and     eax, 0B0h
0x14006788b  or      ecx, eax
0x14006788d  shl     ecx, 3
0x140067890  or      ecx, 206h
0x140067896  mov     dword ptr [rsp+48h+var_28], ecx
0x14006789a  jmp     short loc_1400678AD
0x14006789c  mov     [rsp+48h+var_28], 0
0x1400678a5  mov     dword ptr [rsp+48h+var_28], 206h
0x1400678ad  mov     rcx, [rbx]
0x1400678b0  add     rbx, 38h ; '8'
0x1400678b4  mov     rax, [rsp+48h+var_28]
0x1400678b9  mov     [rcx], rax
0x1400678bc  jmp     short loc_1400678C8
0x1400678be  cmp     qword ptr [rbx], 0
0x1400678c2  jnz     short loc_1400678CF
0x1400678c4  add     rbx, 8
0x1400678c8  cmp     rbx, rsi
0x1400678cb  jb      short loc_1400678BE
0x1400678cd  jmp     short loc_140067912
0x1400678cf  test    rbx, rbx
0x1400678d2  jnz     loc_1400677ED
0x1400678d8  jmp     short loc_140067912
0x1400678da  mov     [rsp+48h+var_28], 0
0x1400678e3  mov     dword ptr [rsp+48h+var_28], 206h
0x1400678eb  mov     rax, [rsp+48h+var_28]
0x1400678f0  mov     rcx, [rbx]
0x1400678f3  add     rbx, 38h ; '8'
0x1400678f7  mov     [rcx], rax
0x1400678fa  jmp     short loc_140067906
0x1400678fc  cmp     qword ptr [rbx], 0
0x140067900  jnz     short loc_14006790D
0x140067902  add     rbx, 8
0x140067906  cmp     rbx, rsi
0x140067909  jb      short loc_1400678FC
0x14006790b  jmp     short loc_140067912
0x14006790d  test    rbx, rbx
0x140067910  jnz     short loc_1400678F0
0x140067912  mov     rcx, [rsp+48h+var_10]
0x140067917  xor     rcx, rsp; StackCookie
0x14006791a  call    __security_check_cookie
0x14006791f  mov     rbx, [rsp+48h+arg_0]
0x140067924  add     rsp, 40h
0x140067928  pop     rsi
0x140067929  retn
```
