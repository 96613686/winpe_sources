# GetModernAppId

- ea: `0x180040620`
- end: `0x18004084a`
- name: `GetModernAppId`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800409a8`

## callees

- `0x18001358c`
- `0x180040620`
- `0x180040e6c`
- `0x1800f8e54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040754`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040754`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040783`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040783`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040829`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040829`

## string_xrefs

- `0x1800407d6`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`
- `0x180040812`: `onecoreuap\windows\dwm\common\telemetryhelper\processinformation\processinformation.cpp`
- `0x180040838`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall GetModernAppId(unsigned int *a1, unsigned __int16 **a2, _DWORD *a3)
{
  __int64 v3; // r14
  _WORD *v7; // r14
  _WORD *v8; // rax
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rsi
  _WORD *v12; // r12
  __int64 v13; // rcx
  _WORD *v14; // rax
  __int64 v15; // rdi
  char *v16; // rbp
  __int64 v17; // rbx
  char *v18; // r9
  _WORD *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rdx
  int i; // ecx
  __int64 v24; // rsi
  const char *v25; // r9
  __int64 v26; // rdi
  unsigned __int16 *v27; // rbx
  int v28; // eax
  unsigned int v29; // edi
  __int64 v31; // rdx
  int v32; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = a1[20];
  *a2 = 0;
  *a3 = 0;
  v7 = (_WORD *)((char *)a1 + v3);
  if ( !v7 )
  {
    v10 = -2147024809;
LABEL_27:
    v31 = 71;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
      (const char *)v10,
      v32);
    return v10;
  }
  v8 = v7;
  v9 = 260;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v9;
  }
  while ( v9 );
  v10 = v9 == 0 ? 0x80070057 : 0;
  v11 = (260 - v9) & -(__int64)(v9 != 0);
  if ( !v9 )
    goto LABEL_27;
  v12 = (_WORD *)((char *)a1 + a1[21]);
  if ( !v12 )
  {
    v10 = -2147024809;
LABEL_30:
    v31 = 76;
    goto LABEL_28;
  }
  v13 = 260;
  v14 = v12;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v10 = v13 == 0 ? 0x80070057 : 0;
  v15 = (260 - v13) & -(__int64)(v13 != 0);
  if ( !v13 )
    goto LABEL_30;
  v16 = (char *)&unk_1801B7F9C;
  v17 = 0;
  v18 = (char *)a1 + a1[19];
  if ( v18 )
  {
    v19 = (_WORD *)((char *)a1 + a1[19]);
    v20 = 0x7FFF;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v20;
    }
    while ( v20 );
    v21 = (0x7FFF - v20) & -(__int64)(v20 != 0);
    if ( v20 )
    {
      v22 = 0;
      for ( i = v21 - 1; i >= 0; --i )
      {
        if ( *(_WORD *)&v18[2 * i] == 92 )
        {
          v22 = i + 1;
          break;
        }
      }
      v16 = &v18[2 * v22];
      v17 = (int)v21 - v22;
    }
  }
  v24 = v17 + v15 + v11;
  *a3 = ((unsigned int)_o__wcsicmp(v16, L"wwahost.exe") != 0) + 1;
  v26 = v24 + 8;
  if ( v24 == -9 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  v27 = (unsigned __int16 *)CoTaskMemAlloc(2 * v26 + 2);
  if ( !v27 )
  {
    v10 = -2147024882;
    v31 = 114;
    goto LABEL_28;
  }
  *v27 = 0;
  v27[v26] = 0;
  v28 = StringCchPrintfW(v27, v24 + 9, aUSS, v7);
  v29 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\windows\\dwm\\common\\telemetryhelper\\processinformation\\processinformation.cpp",
      (const char *)(unsigned int)v28,
      (int)v12);
    CoTaskMemFree(v27);
    return v29;
  }
  else
  {
    *a2 = v27;
    return 0;
  }
}

```

## disassembly

```asm
0x180040620  push    rbx
0x180040622  push    rbp
0x180040623  push    rsi
0x180040624  push    rdi
0x180040625  push    r12
0x180040627  push    r13
0x180040629  push    r14
0x18004062b  push    r15
0x18004062d  sub     rsp, 38h
0x180040631  mov     r14d, [rcx+50h]
0x180040635  mov     r13, r8
0x180040638  xor     r8d, r8d
0x18004063b  mov     r15, rdx
0x18004063e  mov     [rdx], r8
0x180040641  mov     r10, rcx
0x180040644  mov     [r13+0], r8d
0x180040648  add     r14, rcx
0x18004064b  jz      loc_1800407C7
0x180040651  mov     r11d, 104h
0x180040657  mov     rax, r14
0x18004065a  mov     r9d, r11d
0x18004065d  cmp     [rax], r8w
0x180040661  jz      short loc_18004066D
0x180040663  add     rax, 2
0x180040667  sub     r9, 1
0x18004066b  jnz     short loc_18004065D
0x18004066d  mov     rax, r9
0x180040670  mov     edx, 80070057h
0x180040675  neg     rax
0x180040678  mov     rcx, r11
0x18004067b  mov     rax, r9
0x18004067e  sbb     ebx, ebx
0x180040680  sub     rcx, r9
0x180040683  not     ebx
0x180040685  and     ebx, edx
0x180040687  neg     rax
0x18004068a  sbb     rsi, rsi
0x18004068d  and     rsi, rcx
0x180040690  test    r9, r9
0x180040693  jz      loc_1800407CC
0x180040699  mov     r12d, [r10+54h]
0x18004069d  add     r12, r10
0x1800406a0  jz      loc_1800407F8
0x1800406a6  mov     rcx, r11
0x1800406a9  mov     rax, r12
0x1800406ac  cmp     [rax], r8w
0x1800406b0  jz      short loc_1800406BC
0x1800406b2  add     rax, 2
0x1800406b6  sub     rcx, 1
0x1800406ba  jnz     short loc_1800406AC
0x1800406bc  mov     rax, rcx
0x1800406bf  neg     rax
0x1800406c2  mov     rax, rcx
0x1800406c5  sbb     ebx, ebx
0x1800406c7  sub     r11, rcx
0x1800406ca  not     ebx
0x1800406cc  and     ebx, edx
0x1800406ce  neg     rax
0x1800406d1  sbb     rdi, rdi
0x1800406d4  and     rdi, r11
0x1800406d7  test    rcx, rcx
0x1800406da  jz      loc_1800407FA
0x1800406e0  mov     r9d, [r10+4Ch]
0x1800406e4  lea     rbp, unk_1801B7F9C
0x1800406eb  mov     rbx, r8
0x1800406ee  add     r9, r10
0x1800406f1  jz      short loc_18004074A
0x1800406f3  mov     edx, 7FFFh
0x1800406f8  mov     rax, r9
0x1800406fb  mov     ecx, edx
0x1800406fd  cmp     [rax], r8w
0x180040701  jz      short loc_18004070D
0x180040703  add     rax, 2
0x180040707  sub     rcx, 1
0x18004070b  jnz     short loc_1800406FD
0x18004070d  sub     rdx, rcx
0x180040710  mov     rax, rcx
0x180040713  neg     rax
0x180040716  sbb     r8, r8
0x180040719  and     r8, rdx
0x18004071c  test    rcx, rcx
0x18004071f  jz      short loc_18004074A
0x180040721  xor     edx, edx
0x180040723  lea     ecx, [r8-1]
0x180040727  test    ecx, ecx
0x180040729  js      short loc_180040740
0x18004072b  movsxd  rax, ecx
0x18004072e  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x180040734  jz      short loc_18004073A
0x180040736  dec     ecx
0x180040738  jmp     short loc_180040727
0x18004073a  lea     eax, [rcx+1]
0x18004073d  movsxd  rdx, eax
0x180040740  movsxd  rbx, r8d
0x180040743  lea     rbp, [r9+rdx*2]
0x180040747  sub     rbx, rdx
0x18004074a  lea     rdx, aWwahostExe; "wwahost.exe"
0x180040751  mov     rcx, rbp
0x180040754  call    cs:__imp__o__wcsicmp
0x18004075a  neg     eax
0x18004075c  lea     rax, [rbx+rdi]
0x180040760  sbb     ecx, ecx
0x180040762  add     rsi, rax
0x180040765  neg     ecx
0x180040767  inc     ecx
0x180040769  mov     [r13+0], ecx
0x18004076d  lea     rdi, [rsi+8]
0x180040771  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180040775  jz      loc_180040833
0x18004077b  lea     rcx, ds:2[rdi*2]; cb
0x180040783  call    cs:__imp_CoTaskMemAlloc
0x180040789  mov     rbx, rax
0x18004078c  test    rax, rax
0x18004078f  jz      short loc_180040801
0x180040791  xor     eax, eax
0x180040793  mov     [rsp+78h+var_50], rbp
0x180040798  mov     [rbx], ax
0x18004079b  lea     r8, aUSS; "U:%s!%s"
0x1800407a2  mov     r9, r14
0x1800407a5  mov     [rbx+rdi*2], ax
0x1800407a9  lea     rdx, [rsi+9]; unsigned __int64
0x1800407ad  mov     qword ptr [rsp+78h+var_58], r12; int
0x1800407b2  mov     rcx, rbx; unsigned __int16 *
0x1800407b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800407ba  mov     edi, eax
0x1800407bc  test    eax, eax
0x1800407be  js      short loc_18004080D
0x1800407c0  mov     [r15], rbx
0x1800407c3  xor     eax, eax
0x1800407c5  jmp     short loc_1800407E7
0x1800407c7  mov     ebx, 80070057h
0x1800407cc  mov     edx, 47h ; 'G'; void *
0x1800407d1  mov     rcx, [rsp+78h]; this
0x1800407d6  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\dwm\\common\\telem"...
0x1800407dd  mov     r9d, ebx; char *
0x1800407e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800407e5  mov     eax, ebx
0x1800407e7  add     rsp, 38h
0x1800407eb  pop     r15
0x1800407ed  pop     r14
0x1800407ef  pop     r13
0x1800407f1  pop     r12
0x1800407f3  pop     rdi
0x1800407f4  pop     rsi
0x1800407f5  pop     rbp
0x1800407f6  pop     rbx
0x1800407f7  retn
0x1800407f8  mov     ebx, edx
0x1800407fa  mov     edx, 4Ch ; 'L'
0x1800407ff  jmp     short loc_1800407D1
0x180040801  mov     ebx, 8007000Eh
0x180040806  mov     edx, 72h ; 'r'
0x18004080b  jmp     short loc_1800407D1
0x18004080d  mov     rcx, [rsp+78h]; this
0x180040812  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\dwm\\common\\telem"...
0x180040819  mov     r9d, edi; char *
0x18004081c  mov     edx, 7Eh ; '~'; void *
0x180040821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040826  mov     rcx, rbx; pv
0x180040829  call    cs:__imp_CoTaskMemFree
0x18004082f  mov     eax, edi
0x180040831  jmp     short loc_1800407E7
0x180040833  mov     rcx, [rsp+78h]; this
0x180040838  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004083f  mov     edx, 0F89h; void *
0x180040844  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
