# WMDSPPropVal2Var

- ea: `0x1800837a4`
- end: `0x180083896`
- name: `WMDSPPropVal2Var`
- size: `242`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180083b10`
- `0x180083ca0`

## callees

- `0x1800837a4`
- `0x180084690`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18008386a`
- `OLEAUT32!__imp_SysAllocString` at `0x18008386a`
- `OLEAUT32!__imp_SysFreeString` at `0x180083861`
- `OLEAUT32!__imp_SysFreeString` at `0x180083875`
- `OLEAUT32!__imp_SysFreeString` at `0x180083861`
- `OLEAUT32!__imp_SysFreeString` at `0x180083875`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008382c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008382c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083817`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083817`

## pseudocode

```c
void __fastcall WMDSPPropVal2Var(__int64 a1, int *a2)
{
  void *v4; // rcx
  unsigned int v5; // eax
  void *v6; // rax
  OLECHAR *v7; // rcx
  BSTR v8; // rsi

  switch ( *(_WORD *)a1 )
  {
    case 3:
    case 4:
      goto LABEL_21;
    case 5:
LABEL_10:
      *(_QWORD *)(a1 + 8) = *(_QWORD *)a2;
      return;
    case 8:
      v7 = *(OLECHAR **)(a1 + 8);
      v8 = 0;
      if ( *(_QWORD *)a2 )
      {
        SysFreeString(v7);
        v8 = SysAllocString(*(const OLECHAR **)a2);
      }
      else
      {
        SysFreeString(v7);
      }
      *(_QWORD *)(a1 + 8) = v8;
      return;
    case 0xB:
      *(_WORD *)(a1 + 8) = *(_WORD *)a2;
      return;
    case 0x13:
LABEL_21:
      *(_DWORD *)(a1 + 8) = *a2;
      return;
    case 0x14:
      goto LABEL_10;
  }
  if ( *(_WORD *)a1 != 65 )
  {
    if ( *(_WORD *)a1 != 72 )
      return;
    goto LABEL_10;
  }
  v4 = *(void **)(a1 + 16);
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = *a2;
  *(_DWORD *)(a1 + 8) = *a2;
  *(_QWORD *)(a1 + 16) = 0;
  if ( v5 )
  {
    v6 = CoTaskMemAlloc(v5);
    *(_QWORD *)(a1 + 16) = v6;
    if ( v6 )
      memcpy_0(v6, *((const void **)a2 + 1), *(unsigned int *)(a1 + 8));
  }
}

```

## disassembly

```asm
0x1800837a4  mov     [rsp+arg_0], rbx
0x1800837a9  mov     [rsp+arg_8], rsi
0x1800837ae  push    rdi
0x1800837af  sub     rsp, 20h
0x1800837b3  movzx   r8d, word ptr [rcx]
0x1800837b7  mov     rdi, rdx
0x1800837ba  mov     rbx, rcx
0x1800837bd  sub     r8d, 3
0x1800837c1  jz      loc_180083881
0x1800837c7  sub     r8d, 1
0x1800837cb  jz      loc_180083881
0x1800837d1  sub     r8d, 1
0x1800837d5  jz      short loc_180083803
0x1800837d7  sub     r8d, 3
0x1800837db  jz      short loc_180083856
0x1800837dd  sub     r8d, 3
0x1800837e1  jz      short loc_18008384D
0x1800837e3  sub     r8d, 8
0x1800837e7  jz      loc_180083881
0x1800837ed  sub     r8d, 1
0x1800837f1  jz      short loc_180083803
0x1800837f3  sub     r8d, 2Dh ; '-'
0x1800837f7  jz      short loc_18008380C
0x1800837f9  cmp     r8d, 7
0x1800837fd  jnz     loc_180083886
0x180083803  mov     rax, [rdx]
0x180083806  mov     [rcx+8], rax
0x18008380a  jmp     short loc_180083886
0x18008380c  mov     rcx, [rcx+10h]; pv
0x180083810  xor     esi, esi
0x180083812  test    rcx, rcx
0x180083815  jz      short loc_18008381D
0x180083817  call    cs:__imp_CoTaskMemFree
0x18008381d  mov     eax, [rdi]
0x18008381f  mov     [rbx+8], eax
0x180083822  mov     [rbx+10h], rsi
0x180083826  test    eax, eax
0x180083828  jz      short loc_180083886
0x18008382a  mov     ecx, eax; cb
0x18008382c  call    cs:__imp_CoTaskMemAlloc
0x180083832  mov     [rbx+10h], rax
0x180083836  test    rax, rax
0x180083839  jz      short loc_180083886
0x18008383b  mov     r8d, [rbx+8]; Size
0x18008383f  mov     rcx, rax; void *
0x180083842  mov     rdx, [rdi+8]; Src
0x180083846  call    memcpy_0
0x18008384b  jmp     short loc_180083886
0x18008384d  movzx   eax, word ptr [rdx]
0x180083850  mov     [rcx+8], ax
0x180083854  jmp     short loc_180083886
0x180083856  mov     rcx, [rcx+8]; bstrString
0x18008385a  xor     esi, esi
0x18008385c  cmp     [rdx], rsi
0x18008385f  jz      short loc_180083875
0x180083861  call    cs:__imp_SysFreeString
0x180083867  mov     rcx, [rdi]; psz
0x18008386a  call    cs:__imp_SysAllocString
0x180083870  mov     rsi, rax
0x180083873  jmp     short loc_18008387B
0x180083875  call    cs:__imp_SysFreeString
0x18008387b  mov     [rbx+8], rsi
0x18008387f  jmp     short loc_180083886
0x180083881  mov     eax, [rdx]
0x180083883  mov     [rcx+8], eax
0x180083886  mov     rbx, [rsp+28h+arg_0]
0x18008388b  mov     rsi, [rsp+28h+arg_8]
0x180083890  add     rsp, 20h
0x180083894  pop     rdi
0x180083895  retn
```
