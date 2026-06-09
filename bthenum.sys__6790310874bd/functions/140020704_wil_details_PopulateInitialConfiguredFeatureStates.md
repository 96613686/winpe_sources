# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140020704`
- end: `0x140020883`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002059c`

## callees

- `0x140007d00`
- `0x140020704`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140020780`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140020780`

## pseudocode

```c
void wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 **i; // rbx
  int v1; // eax
  __int64 *v2; // rcx
  __int64 *v3; // rcx
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+28h] [rbp-20h] BYREF
  int v6; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; ; ++i )
  {
    if ( i >= (__int64 **)wil_details_featureDescriptors_z )
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
    while ( i < (__int64 **)wil_details_featureDescriptors_z )
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
  *v3 = 518;
  while ( i < (__int64 **)wil_details_featureDescriptors_z )
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
0x140020704  mov     [rsp+arg_0], rbx
0x140020709  push    rsi
0x14002070a  sub     rsp, 40h
0x14002070e  mov     rax, cs:__security_cookie
0x140020715  xor     rax, rsp
0x140020718  mov     [rsp+48h+var_10], rax
0x14002071d  lea     rbx, wil_details_featureDescriptors_a
0x140020724  lea     rsi, wil_details_featureDescriptors_z
0x14002072b  jmp     short loc_14002073B
0x14002072d  cmp     qword ptr [rbx], 0
0x140020731  jnz     loc_140020827
0x140020737  add     rbx, 8
0x14002073b  cmp     rbx, rsi
0x14002073e  jb      short loc_14002072D
0x140020740  jmp     loc_14002086A
0x140020745  xor     eax, eax
0x140020747  mov     [rsp+48h+var_20], rax
0x14002074c  mov     [rsp+48h+var_18], eax
0x140020750  mov     [rsp+48h+var_28], rax
0x140020755  cmp     [rbx+1Dh], al
0x140020758  jnz     loc_1400207F4
0x14002075e  cmp     [rbx+1Eh], al
0x140020761  jnz     loc_1400207F4
0x140020767  mov     al, [rbx+1Ch]
0x14002076a  lea     r9, [rsp+48h+var_20]
0x14002076f  mov     ecx, [rbx+18h]
0x140020772  lea     r8, [rsp+48h+var_28]
0x140020777  xor     edx, edx
0x140020779  sub     al, 2
0x14002077b  cmp     al, 1
0x14002077d  setnbe  dl
0x140020780  call    cs:__imp_RtlQueryFeatureConfiguration
0x140020787  nop     dword ptr [rax+rax+00h]
0x14002078c  cmp     eax, 80000022h
0x140020791  jz      loc_140020832
0x140020797  cmp     eax, 0C0000225h
0x14002079c  jz      short loc_1400207F4
0x14002079e  test    eax, eax
0x1400207a0  jz      short loc_1400207C9
0x1400207a2  cmp     eax, 117h
0x1400207a7  jnz     short loc_1400207F4
0x1400207a9  mov     eax, dword ptr [rsp+48h+var_20+4]
0x1400207ad  and     eax, 80h
0x1400207b2  mov     [rsp+48h+var_28], 0
0x1400207bb  shl     eax, 3
0x1400207be  or      eax, 206h
0x1400207c3  mov     dword ptr [rsp+48h+var_28], eax
0x1400207c7  jmp     short loc_140020805
0x1400207c9  mov     eax, dword ptr [rsp+48h+var_20+4]
0x1400207cd  mov     ecx, eax
0x1400207cf  and     ecx, 40h
0x1400207d2  mov     [rsp+48h+var_28], 0
0x1400207db  shl     ecx, 2
0x1400207de  and     eax, 0B0h
0x1400207e3  or      ecx, eax
0x1400207e5  shl     ecx, 3
0x1400207e8  or      ecx, 206h
0x1400207ee  mov     dword ptr [rsp+48h+var_28], ecx
0x1400207f2  jmp     short loc_140020805
0x1400207f4  mov     [rsp+48h+var_28], 0
0x1400207fd  mov     dword ptr [rsp+48h+var_28], 206h
0x140020805  mov     rcx, [rbx]
0x140020808  add     rbx, 38h ; '8'
0x14002080c  mov     rax, [rsp+48h+var_28]
0x140020811  mov     [rcx], rax
0x140020814  jmp     short loc_140020820
0x140020816  cmp     qword ptr [rbx], 0
0x14002081a  jnz     short loc_140020827
0x14002081c  add     rbx, 8
0x140020820  cmp     rbx, rsi
0x140020823  jb      short loc_140020816
0x140020825  jmp     short loc_14002086A
0x140020827  test    rbx, rbx
0x14002082a  jnz     loc_140020745
0x140020830  jmp     short loc_14002086A
0x140020832  mov     [rsp+48h+var_28], 0
0x14002083b  mov     dword ptr [rsp+48h+var_28], 206h
0x140020843  mov     rax, [rsp+48h+var_28]
0x140020848  mov     rcx, [rbx]
0x14002084b  add     rbx, 38h ; '8'
0x14002084f  mov     [rcx], rax
0x140020852  jmp     short loc_14002085E
0x140020854  cmp     qword ptr [rbx], 0
0x140020858  jnz     short loc_140020865
0x14002085a  add     rbx, 8
0x14002085e  cmp     rbx, rsi
0x140020861  jb      short loc_140020854
0x140020863  jmp     short loc_14002086A
0x140020865  test    rbx, rbx
0x140020868  jnz     short loc_140020848
0x14002086a  mov     rcx, [rsp+48h+var_10]
0x14002086f  xor     rcx, rsp; StackCookie
0x140020872  call    __security_check_cookie
0x140020877  mov     rbx, [rsp+48h+arg_0]
0x14002087c  add     rsp, 40h
0x140020880  pop     rsi
0x140020881  retn
```
