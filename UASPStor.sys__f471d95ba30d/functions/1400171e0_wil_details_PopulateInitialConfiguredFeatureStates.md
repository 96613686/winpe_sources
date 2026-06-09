# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x1400171e0`
- end: `0x14001735f`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140017078`

## callees

- `0x14000d7f0`
- `0x1400171e0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001725c`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001725c`

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
0x1400171e0  mov     [rsp+arg_0], rbx
0x1400171e5  push    rsi
0x1400171e6  sub     rsp, 40h
0x1400171ea  mov     rax, cs:__security_cookie
0x1400171f1  xor     rax, rsp
0x1400171f4  mov     [rsp+48h+var_10], rax
0x1400171f9  lea     rbx, wil_details_featureDescriptors_a
0x140017200  lea     rsi, wil_details_featureDescriptors_a
0x140017207  jmp     short loc_140017217
0x140017209  cmp     qword ptr [rbx], 0
0x14001720d  jnz     loc_140017303
0x140017213  add     rbx, 8
0x140017217  cmp     rbx, rsi
0x14001721a  jb      short loc_140017209
0x14001721c  jmp     loc_140017346
0x140017221  xor     eax, eax
0x140017223  mov     [rsp+48h+var_20], rax
0x140017228  mov     [rsp+48h+var_18], eax
0x14001722c  mov     [rsp+48h+var_28], rax
0x140017231  cmp     [rbx+1Dh], al
0x140017234  jnz     loc_1400172D0
0x14001723a  cmp     [rbx+1Eh], al
0x14001723d  jnz     loc_1400172D0
0x140017243  mov     al, [rbx+1Ch]
0x140017246  lea     r9, [rsp+48h+var_20]
0x14001724b  mov     ecx, [rbx+18h]
0x14001724e  lea     r8, [rsp+48h+var_28]
0x140017253  xor     edx, edx
0x140017255  sub     al, 2
0x140017257  cmp     al, 1
0x140017259  setnbe  dl
0x14001725c  call    cs:__imp_RtlQueryFeatureConfiguration
0x140017263  nop     dword ptr [rax+rax+00h]
0x140017268  cmp     eax, 80000022h
0x14001726d  jz      loc_14001730E
0x140017273  cmp     eax, 0C0000225h
0x140017278  jz      short loc_1400172D0
0x14001727a  test    eax, eax
0x14001727c  jz      short loc_1400172A5
0x14001727e  cmp     eax, 117h
0x140017283  jnz     short loc_1400172D0
0x140017285  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140017289  and     eax, 80h
0x14001728e  mov     [rsp+48h+var_28], 0
0x140017297  shl     eax, 3
0x14001729a  or      eax, 206h
0x14001729f  mov     dword ptr [rsp+48h+var_28], eax
0x1400172a3  jmp     short loc_1400172E1
0x1400172a5  mov     eax, dword ptr [rsp+48h+var_20+4]
0x1400172a9  mov     ecx, eax
0x1400172ab  and     ecx, 40h
0x1400172ae  mov     [rsp+48h+var_28], 0
0x1400172b7  shl     ecx, 2
0x1400172ba  and     eax, 0B0h
0x1400172bf  or      ecx, eax
0x1400172c1  shl     ecx, 3
0x1400172c4  or      ecx, 206h
0x1400172ca  mov     dword ptr [rsp+48h+var_28], ecx
0x1400172ce  jmp     short loc_1400172E1
0x1400172d0  mov     [rsp+48h+var_28], 0
0x1400172d9  mov     dword ptr [rsp+48h+var_28], 206h
0x1400172e1  mov     rcx, [rbx]
0x1400172e4  add     rbx, 38h ; '8'
0x1400172e8  mov     rax, [rsp+48h+var_28]
0x1400172ed  mov     [rcx], rax
0x1400172f0  jmp     short loc_1400172FC
0x1400172f2  cmp     qword ptr [rbx], 0
0x1400172f6  jnz     short loc_140017303
0x1400172f8  add     rbx, 8
0x1400172fc  cmp     rbx, rsi
0x1400172ff  jb      short loc_1400172F2
0x140017301  jmp     short loc_140017346
0x140017303  test    rbx, rbx
0x140017306  jnz     loc_140017221
0x14001730c  jmp     short loc_140017346
0x14001730e  mov     [rsp+48h+var_28], 0
0x140017317  mov     dword ptr [rsp+48h+var_28], 206h
0x14001731f  mov     rax, [rsp+48h+var_28]
0x140017324  mov     rcx, [rbx]
0x140017327  add     rbx, 38h ; '8'
0x14001732b  mov     [rcx], rax
0x14001732e  jmp     short loc_14001733A
0x140017330  cmp     qword ptr [rbx], 0
0x140017334  jnz     short loc_140017341
0x140017336  add     rbx, 8
0x14001733a  cmp     rbx, rsi
0x14001733d  jb      short loc_140017330
0x14001733f  jmp     short loc_140017346
0x140017341  test    rbx, rbx
0x140017344  jnz     short loc_140017324
0x140017346  mov     rcx, [rsp+48h+var_10]
0x14001734b  xor     rcx, rsp; StackCookie
0x14001734e  call    __security_check_cookie
0x140017353  mov     rbx, [rsp+48h+arg_0]
0x140017358  add     rsp, 40h
0x14001735c  pop     rsi
0x14001735d  retn
```
