# EdppPolicyOverride

- ea: `0x14002d868`
- end: `0x14002da55`
- name: `EdppPolicyOverride`
- size: `493`
- prototype: `char __fastcall(_QWORD *, _DWORD *, _QWORD *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140003ec0`

## callees

- `0x14000421c`
- `0x140006b20`
- `0x140006c40`
- `0x140006f40`
- `0x14002948c`
- `0x14002d868`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!wcsstr` at `0x14002d9ae`
- `ntoskrnl!wcsstr` at `0x14002d9ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002d8fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002d957`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002d8fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002d957`

## string_xrefs

- `0x14002d89d`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\EDP`

## pseudocode

```c
char __fastcall EdppPolicyOverride(_QWORD *a1, _DWORD *a2, _QWORD *a3, _QWORD *a4, _DWORD *a5)
{
  const void *v6; // rcx
  void *v7; // r14
  wchar_t **v8; // rsi
  char v9; // r13
  wchar_t *v10; // rdi
  unsigned int v11; // r12d
  size_t v12; // rdx
  wchar_t *i; // rbx
  size_t v14; // r15
  int v15; // ecx
  __int64 v17; // [rsp+20h] [rbp-58h]
  struct _UNICODE_STRING v18; // [rsp+28h] [rbp-50h] BYREF
  wchar_t *Src[2]; // [rsp+38h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-30h] BYREF
  struct _UNICODE_STRING v21; // [rsp+58h] [rbp-20h] BYREF

  *(_QWORD *)&v18.Length = 9830548;
  v6 = (const void *)a1[9];
  v18.Buffer = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\EDP";
  v7 = 0;
  v8 = &off_140009DF0;
  v9 = 0;
  *(_OWORD *)Src = 0;
  DestinationString = 0;
  v10 = 0;
  v11 = 0;
  v17 = *(_QWORD *)((char *)a1 + (memcmp(v6, qword_1400191D8, 0x10u) != 0 ? 8 : 0) + 16);
  while ( v11 < 7 )
  {
    RtlInitUnicodeString(&DestinationString, *v8);
    if ( (int)AiRegReadStringValue(0, &v18, &DestinationString, (__int64)Src) >= 0 )
    {
      v10 = Src[1];
      for ( i = Src[1]; ; i += v14 + 1 )
      {
        if ( !*i )
        {
          AiFree(v10);
          goto LABEL_12;
        }
        v14 = wcsnlen_s(i, v12);
        if ( !v14 )
          goto LABEL_17;
        v21 = 0;
        RtlInitUnicodeString(&v21, i);
        if ( !v7 )
        {
          v7 = (void *)AiAlloc(*(unsigned __int16 *)(v17 + 2) + 2LL);
          memset(v7, 0, *(unsigned __int16 *)(v17 + 2) + 2LL);
          memmove(v7, *(const void **)(v17 + 8), *(unsigned __int16 *)(v17 + 2));
        }
        if ( wcsstr((const wchar_t *)v7, i) )
          break;
      }
      *a2 = *((_DWORD *)v8 + 2);
      *a3 = v8[2];
      if ( *((_BYTE *)v8 + 24) )
      {
        *a4 = *(_QWORD *)(*a1 + 24LL);
        v15 = *(_DWORD *)(*a1 + 32LL);
      }
      else
      {
        v15 = 0;
        *a4 = 0;
      }
      v9 = 1;
      *a5 = v15;
      break;
    }
LABEL_12:
    v10 = 0;
    v8 += 4;
    Src[1] = 0;
    ++v11;
  }
LABEL_17:
  AiFree(v10);
  AiFree(v7);
  return v9;
}

```

## disassembly

```asm
0x14002d868  mov     rax, rsp
0x14002d86b  mov     [rax+20h], r9
0x14002d86f  mov     [rax+18h], r8
0x14002d873  mov     [rax+10h], rdx
0x14002d877  mov     [rax+8], rcx
0x14002d87b  push    rbp
0x14002d87c  push    rbx
0x14002d87d  push    rsi
0x14002d87e  push    rdi
0x14002d87f  push    r12
0x14002d881  push    r13
0x14002d883  push    r14
0x14002d885  push    r15
0x14002d887  mov     rbp, rsp
0x14002d88a  sub     rsp, 78h
0x14002d88e  mov     rbx, rcx
0x14002d891  mov     [rbp+var_50], 960094h
0x14002d899  mov     rcx, [rcx+48h]; Buf1
0x14002d89d  lea     rax, aRegistryMachin_2; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x14002d8a4  xorps   xmm0, xmm0
0x14002d8a7  mov     [rbp+var_48], rax
0x14002d8ab  xorps   xmm1, xmm1
0x14002d8ae  lea     rdx, qword_1400191D8; Buf2
0x14002d8b5  xor     r14d, r14d
0x14002d8b8  lea     rsi, off_140009DF0; "ExeAllow"
0x14002d8bf  xor     r13b, r13b
0x14002d8c2  movups  xmmword ptr [rbp+Src], xmm0
0x14002d8c6  lea     r8d, [r14+10h]; Size
0x14002d8ca  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14002d8ce  call    memcmp
0x14002d8d3  mov     rdi, [rbp+Src+8]
0x14002d8d7  neg     eax
0x14002d8d9  sbb     rcx, rcx
0x14002d8dc  and     ecx, 8
0x14002d8df  xor     r12d, r12d
0x14002d8e2  mov     rax, [rcx+rbx+10h]
0x14002d8e7  mov     [rbp+var_58], rax
0x14002d8eb  cmp     r12d, 7
0x14002d8ef  jnb     loc_14002DA30
0x14002d8f5  mov     rdx, [rsi]; SourceString
0x14002d8f8  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002d8fc  call    cs:__imp_RtlInitUnicodeString
0x14002d903  nop     dword ptr [rax+rax+00h]
0x14002d908  lea     r9, [rbp+Src]
0x14002d90c  xor     ecx, ecx
0x14002d90e  lea     r8, [rbp+DestinationString]
0x14002d912  lea     rdx, [rbp+var_50]
0x14002d916  call    AiRegReadStringValue
0x14002d91b  test    eax, eax
0x14002d91d  js      loc_14002D9D4
0x14002d923  mov     rdi, [rbp+Src+8]
0x14002d927  mov     rbx, rdi
0x14002d92a  xor     eax, eax
0x14002d92c  cmp     ax, [rbx]
0x14002d92f  jz      loc_14002D9CC
0x14002d935  mov     rcx, rbx; Src
0x14002d938  call    wcsnlen_s
0x14002d93d  mov     r15, rax
0x14002d940  test    rax, rax
0x14002d943  jz      loc_14002DA30
0x14002d949  xorps   xmm0, xmm0
0x14002d94c  lea     rcx, [rbp+var_20]; DestinationString
0x14002d950  mov     rdx, rbx; SourceString
0x14002d953  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x14002d957  call    cs:__imp_RtlInitUnicodeString
0x14002d95e  nop     dword ptr [rax+rax+00h]
0x14002d963  test    r14, r14
0x14002d966  jnz     short loc_14002D9A8
0x14002d968  mov     rax, [rbp+var_58]
0x14002d96c  movzx   ecx, word ptr [rax+2]
0x14002d970  add     rcx, 2
0x14002d974  call    AiAlloc
0x14002d979  mov     r14, rax
0x14002d97c  xor     edx, edx; Val
0x14002d97e  mov     rax, [rbp+var_58]
0x14002d982  mov     rcx, r14; void *
0x14002d985  movzx   r8d, word ptr [rax+2]
0x14002d98a  add     r8, 2; Size
0x14002d98e  call    memset
0x14002d993  mov     rax, [rbp+var_58]
0x14002d997  mov     rcx, r14; void *
0x14002d99a  movzx   r8d, word ptr [rax+2]; Size
0x14002d99f  mov     rdx, [rax+8]; Src
0x14002d9a3  call    memmove
0x14002d9a8  mov     rdx, rbx; SubStr
0x14002d9ab  mov     rcx, r14; Str
0x14002d9ae  call    cs:__imp_wcsstr
0x14002d9b5  nop     dword ptr [rax+rax+00h]
0x14002d9ba  test    rax, rax
0x14002d9bd  jnz     short loc_14002D9E6
0x14002d9bf  lea     rbx, [rbx+r15*2]
0x14002d9c3  add     rbx, 2
0x14002d9c7  jmp     loc_14002D92A
0x14002d9cc  mov     rcx, rdi
0x14002d9cf  call    AiFree
0x14002d9d4  xor     edi, edi
0x14002d9d6  add     rsi, 20h ; ' '
0x14002d9da  mov     [rbp+Src+8], rdi
0x14002d9de  inc     r12d
0x14002d9e1  jmp     loc_14002D8EB
0x14002d9e6  mov     rcx, [rbp+arg_8]
0x14002d9ea  mov     eax, [rsi+8]
0x14002d9ed  mov     [rcx], eax
0x14002d9ef  mov     rcx, [rbp+arg_10]
0x14002d9f3  mov     rax, [rsi+10h]
0x14002d9f7  mov     [rcx], rax
0x14002d9fa  cmp     [rsi+18h], r13b
0x14002d9fe  jz      short loc_14002DA1A
0x14002da00  mov     rdx, [rbp+arg_0]
0x14002da04  mov     rax, [rdx]
0x14002da07  mov     rcx, [rax+18h]
0x14002da0b  mov     rax, [rbp+arg_18]
0x14002da0f  mov     [rax], rcx
0x14002da12  mov     rax, [rdx]
0x14002da15  mov     ecx, [rax+20h]
0x14002da18  jmp     short loc_14002DA27
0x14002da1a  mov     rax, [rbp+arg_18]
0x14002da1e  xor     ecx, ecx
0x14002da20  mov     qword ptr [rax], 0
0x14002da27  mov     rax, [rbp+arg_20]
0x14002da2b  mov     r13b, 1
0x14002da2e  mov     [rax], ecx
0x14002da30  mov     rcx, rdi
0x14002da33  call    AiFree
0x14002da38  mov     rcx, r14
0x14002da3b  call    AiFree
0x14002da40  mov     al, r13b
0x14002da43  add     rsp, 78h
0x14002da47  pop     r15
0x14002da49  pop     r14
0x14002da4b  pop     r13
0x14002da4d  pop     r12
0x14002da4f  pop     rdi
0x14002da50  pop     rsi
0x14002da51  pop     rbx
0x14002da52  pop     rbp
0x14002da53  retn
```
