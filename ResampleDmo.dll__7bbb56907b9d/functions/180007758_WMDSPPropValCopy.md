# WMDSPPropValCopy

- ea: `0x180007758`
- end: `0x18000783e`
- name: `WMDSPPropValCopy`
- size: `230`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800074f0`
- `0x180083a70`
- `0x180083ad0`
- `0x180084090`

## callees

- `0x180007758`
- `0x180084690`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007825`
- `OLEAUT32!__imp_SysAllocString` at `0x180007825`
- `OLEAUT32!__imp_SysFreeString` at `0x18000781c`
- `OLEAUT32!__imp_SysFreeString` at `0x180007830`
- `OLEAUT32!__imp_SysFreeString` at `0x18000781c`
- `OLEAUT32!__imp_SysFreeString` at `0x180007830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800077e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800077e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800077cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800077cf`

## pseudocode

```c
void __fastcall WMDSPPropValCopy(__int16 a1, OLECHAR **a2, int *a3)
{
  OLECHAR *v5; // rcx
  unsigned int v6; // eax
  OLECHAR *v7; // rax
  OLECHAR *v8; // rcx
  BSTR v9; // rsi

  switch ( a1 )
  {
    case 3:
    case 4:
      goto LABEL_2;
    case 5:
LABEL_12:
      *a2 = *(OLECHAR **)a3;
      return;
    case 8:
      v8 = *a2;
      v9 = 0;
      if ( *(_QWORD *)a3 )
      {
        SysFreeString(v8);
        v9 = SysAllocString(*(const OLECHAR **)a3);
      }
      else
      {
        SysFreeString(v8);
      }
      *a2 = v9;
      return;
    case 11:
      *(_WORD *)a2 = *(_WORD *)a3;
      return;
    case 19:
LABEL_2:
      *(_DWORD *)a2 = *a3;
      return;
    case 20:
      goto LABEL_12;
    case 65:
      v5 = a2[1];
      if ( v5 )
        CoTaskMemFree(v5);
      v6 = *a3;
      *(_DWORD *)a2 = *a3;
      a2[1] = 0;
      if ( v6 )
      {
        v7 = (OLECHAR *)CoTaskMemAlloc(v6);
        a2[1] = v7;
        if ( v7 )
          memcpy_0(v7, *((const void **)a3 + 1), *(unsigned int *)a2);
      }
      break;
    case 72:
      goto LABEL_12;
  }
}

```

## disassembly

```asm
0x180007758  mov     [rsp+arg_0], rbx
0x18000775d  mov     [rsp+arg_8], rsi
0x180007762  push    rdi
0x180007763  sub     rsp, 20h
0x180007767  movzx   r9d, cx
0x18000776b  mov     rdi, r8
0x18000776e  mov     rbx, rdx
0x180007771  sub     r9d, 3
0x180007775  jnz     short loc_18000778C
0x180007777  mov     eax, [r8]
0x18000777a  mov     [rdx], eax
0x18000777c  mov     rbx, [rsp+28h+arg_0]
0x180007781  mov     rsi, [rsp+28h+arg_8]
0x180007786  add     rsp, 20h
0x18000778a  pop     rdi
0x18000778b  retn
0x18000778c  sub     r9d, 1
0x180007790  jz      short loc_180007777
0x180007792  sub     r9d, 1
0x180007796  jz      short loc_1800077BC
0x180007798  sub     r9d, 3
0x18000779c  jz      short loc_180007812
0x18000779e  sub     r9d, 3
0x1800077a2  jz      short loc_180007806
0x1800077a4  sub     r9d, 8
0x1800077a8  jz      short loc_180007777
0x1800077aa  sub     r9d, 1
0x1800077ae  jz      short loc_1800077BC
0x1800077b0  sub     r9d, 2Dh ; '-'
0x1800077b4  jz      short loc_1800077C4
0x1800077b6  cmp     r9d, 7
0x1800077ba  jnz     short loc_18000777C
0x1800077bc  mov     rax, [r8]
0x1800077bf  mov     [rdx], rax
0x1800077c2  jmp     short loc_18000777C
0x1800077c4  mov     rcx, [rdx+8]; pv
0x1800077c8  xor     esi, esi
0x1800077ca  test    rcx, rcx
0x1800077cd  jz      short loc_1800077D5
0x1800077cf  call    cs:__imp_CoTaskMemFree
0x1800077d5  mov     eax, [rdi]
0x1800077d7  mov     [rbx], eax
0x1800077d9  mov     [rbx+8], rsi
0x1800077dd  test    eax, eax
0x1800077df  jz      short loc_18000777C
0x1800077e1  mov     ecx, eax; cb
0x1800077e3  call    cs:__imp_CoTaskMemAlloc
0x1800077e9  mov     [rbx+8], rax
0x1800077ed  test    rax, rax
0x1800077f0  jz      short loc_18000777C
0x1800077f2  mov     r8d, [rbx]; Size
0x1800077f5  mov     rcx, rax; void *
0x1800077f8  mov     rdx, [rdi+8]; Src
0x1800077fc  call    memcpy_0
0x180007801  jmp     loc_18000777C
0x180007806  movzx   eax, word ptr [r8]
0x18000780a  mov     [rdx], ax
0x18000780d  jmp     loc_18000777C
0x180007812  mov     rcx, [rdx]; bstrString
0x180007815  xor     esi, esi
0x180007817  cmp     [r8], rsi
0x18000781a  jz      short loc_180007830
0x18000781c  call    cs:__imp_SysFreeString
0x180007822  mov     rcx, [rdi]; psz
0x180007825  call    cs:__imp_SysAllocString
0x18000782b  mov     rsi, rax
0x18000782e  jmp     short loc_180007836
0x180007830  call    cs:__imp_SysFreeString
0x180007836  mov     [rbx], rsi
0x180007839  jmp     loc_18000777C
```
