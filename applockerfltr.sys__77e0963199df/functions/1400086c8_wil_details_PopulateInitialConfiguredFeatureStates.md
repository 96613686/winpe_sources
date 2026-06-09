# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x1400086c8`
- end: `0x140008847`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140008560`

## callees

- `0x140001820`
- `0x1400086c8`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140008744`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140008744`

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
0x1400086c8  mov     [rsp+arg_0], rbx
0x1400086cd  push    rsi
0x1400086ce  sub     rsp, 40h
0x1400086d2  mov     rax, cs:__security_cookie
0x1400086d9  xor     rax, rsp
0x1400086dc  mov     [rsp+48h+var_10], rax
0x1400086e1  lea     rbx, wil_details_featureDescriptors_a
0x1400086e8  lea     rsi, wil_details_featureDescriptors_a
0x1400086ef  jmp     short loc_1400086FF
0x1400086f1  cmp     qword ptr [rbx], 0
0x1400086f5  jnz     loc_1400087EB
0x1400086fb  add     rbx, 8
0x1400086ff  cmp     rbx, rsi
0x140008702  jb      short loc_1400086F1
0x140008704  jmp     loc_14000882E
0x140008709  xor     eax, eax
0x14000870b  mov     [rsp+48h+var_20], rax
0x140008710  mov     [rsp+48h+var_18], eax
0x140008714  mov     [rsp+48h+var_28], rax
0x140008719  cmp     [rbx+1Dh], al
0x14000871c  jnz     loc_1400087B8
0x140008722  cmp     [rbx+1Eh], al
0x140008725  jnz     loc_1400087B8
0x14000872b  mov     al, [rbx+1Ch]
0x14000872e  lea     r9, [rsp+48h+var_20]
0x140008733  mov     ecx, [rbx+18h]
0x140008736  lea     r8, [rsp+48h+var_28]
0x14000873b  xor     edx, edx
0x14000873d  sub     al, 2
0x14000873f  cmp     al, 1
0x140008741  setnbe  dl
0x140008744  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000874b  nop     dword ptr [rax+rax+00h]
0x140008750  cmp     eax, 80000022h
0x140008755  jz      loc_1400087F6
0x14000875b  cmp     eax, 0C0000225h
0x140008760  jz      short loc_1400087B8
0x140008762  test    eax, eax
0x140008764  jz      short loc_14000878D
0x140008766  cmp     eax, 117h
0x14000876b  jnz     short loc_1400087B8
0x14000876d  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140008771  and     eax, 80h
0x140008776  mov     [rsp+48h+var_28], 0
0x14000877f  shl     eax, 3
0x140008782  or      eax, 206h
0x140008787  mov     dword ptr [rsp+48h+var_28], eax
0x14000878b  jmp     short loc_1400087C9
0x14000878d  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140008791  mov     ecx, eax
0x140008793  and     ecx, 40h
0x140008796  mov     [rsp+48h+var_28], 0
0x14000879f  shl     ecx, 2
0x1400087a2  and     eax, 0B0h
0x1400087a7  or      ecx, eax
0x1400087a9  shl     ecx, 3
0x1400087ac  or      ecx, 206h
0x1400087b2  mov     dword ptr [rsp+48h+var_28], ecx
0x1400087b6  jmp     short loc_1400087C9
0x1400087b8  mov     [rsp+48h+var_28], 0
0x1400087c1  mov     dword ptr [rsp+48h+var_28], 206h
0x1400087c9  mov     rcx, [rbx]
0x1400087cc  add     rbx, 38h ; '8'
0x1400087d0  mov     rax, [rsp+48h+var_28]
0x1400087d5  mov     [rcx], rax
0x1400087d8  jmp     short loc_1400087E4
0x1400087da  cmp     qword ptr [rbx], 0
0x1400087de  jnz     short loc_1400087EB
0x1400087e0  add     rbx, 8
0x1400087e4  cmp     rbx, rsi
0x1400087e7  jb      short loc_1400087DA
0x1400087e9  jmp     short loc_14000882E
0x1400087eb  test    rbx, rbx
0x1400087ee  jnz     loc_140008709
0x1400087f4  jmp     short loc_14000882E
0x1400087f6  mov     [rsp+48h+var_28], 0
0x1400087ff  mov     dword ptr [rsp+48h+var_28], 206h
0x140008807  mov     rax, [rsp+48h+var_28]
0x14000880c  mov     rcx, [rbx]
0x14000880f  add     rbx, 38h ; '8'
0x140008813  mov     [rcx], rax
0x140008816  jmp     short loc_140008822
0x140008818  cmp     qword ptr [rbx], 0
0x14000881c  jnz     short loc_140008829
0x14000881e  add     rbx, 8
0x140008822  cmp     rbx, rsi
0x140008825  jb      short loc_140008818
0x140008827  jmp     short loc_14000882E
0x140008829  test    rbx, rbx
0x14000882c  jnz     short loc_14000880C
0x14000882e  mov     rcx, [rsp+48h+var_10]
0x140008833  xor     rcx, rsp; StackCookie
0x140008836  call    __security_check_cookie
0x14000883b  mov     rbx, [rsp+48h+arg_0]
0x140008840  add     rsp, 40h
0x140008844  pop     rsi
0x140008845  retn
```
