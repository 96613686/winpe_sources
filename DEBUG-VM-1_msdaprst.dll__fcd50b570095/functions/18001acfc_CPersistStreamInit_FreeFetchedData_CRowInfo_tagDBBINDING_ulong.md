# CPersistStreamInit::FreeFetchedData(CRowInfo &,tagDBBINDING *,ulong)

- ea: `0x18001acfc`
- end: `0x18001adf6`
- name: `?FreeFetchedData@CPersistStreamInit@@AEAAXAEAVCRowInfo@@PEAUtagDBBINDING@@K@Z`
- size: `250`
- prototype: `void __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *, struct tagDBBINDING *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001d168`
- `0x18001e44c`

## callees

- `0x18001acfc`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001ad89`
- `ole32!CoTaskMemFree` at `0x18001ad89`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad50`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad50`
- `OLEAUT32!__imp_VariantClear` at `0x18001add9`
- `OLEAUT32!__imp_VariantClear` at `0x18001add9`

## pseudocode

```c
void __fastcall CPersistStreamInit::FreeFetchedData(
        CPersistStreamInit *this,
        struct CRowInfo *a2,
        struct tagDBBINDING *a3,
        unsigned int a4)
{
  unsigned int i; // edi
  __int64 v8; // rdx
  __int16 v9; // cx
  OLECHAR *v10; // rcx
  void *v11; // rcx
  DBBYTEOFFSET v12; // rcx
  DBBYTEOFFSET obValue; // rax
  __int64 v14; // rcx
  VARIANTARG *v15; // rcx

  if ( a4 )
  {
    for ( i = 0; i < a4; ++i )
    {
      v8 = *((_QWORD *)a2 + 11);
      if ( (*(_DWORD *)(v8 + a3->obStatus) & 0xFFFFFFFB) == 0 )
      {
        v9 = a3->wType & 0xBFFF;
        if ( v9 == 8 )
        {
          v10 = *(OLECHAR **)(v8 + a3->obValue);
          if ( v10 )
          {
            SysFreeString(v10);
            goto LABEL_15;
          }
        }
        else if ( (a3->wType & 0x4000) == 0 || a3->dwMemOwner || (unsigned __int16)(v9 - 128) > 2u )
        {
          if ( v9 != 13 )
          {
            if ( v9 == 12 )
            {
              v15 = (VARIANTARG *)(v8 + a3->obValue);
              if ( v15 )
                VariantClear(v15);
            }
            goto LABEL_20;
          }
          v14 = *(_QWORD *)(v8 + a3->obValue);
          if ( v14 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_15:
            v12 = *((_QWORD *)a2 + 11);
            obValue = a3->obValue;
LABEL_16:
            *(_QWORD *)(v12 + obValue) = 0;
          }
        }
        else
        {
          v11 = *(void **)(v8 + a3->obValue);
          if ( v11 )
          {
            CoTaskMemFree(v11);
            v12 = a3->obValue;
            obValue = *((_QWORD *)a2 + 11);
            goto LABEL_16;
          }
        }
      }
LABEL_20:
      ++a3;
    }
  }
}

```

## disassembly

```asm
0x18001acfc  test    r9d, r9d
0x18001acff  jz      locret_18001ADF5
0x18001ad05  push    rbx
0x18001ad06  push    rbp
0x18001ad07  push    rsi
0x18001ad08  push    rdi
0x18001ad09  sub     rsp, 28h
0x18001ad0d  mov     ebp, r9d
0x18001ad10  mov     rbx, r8
0x18001ad13  mov     rsi, rdx
0x18001ad16  xor     edi, edi
0x18001ad18  mov     rdx, [rsi+58h]
0x18001ad1c  mov     rax, [rbx+18h]
0x18001ad20  test    dword ptr [rdx+rax], 0FFFFFFFBh
0x18001ad27  jnz     loc_18001ADDF
0x18001ad2d  movzx   ecx, word ptr [rbx+54h]
0x18001ad31  mov     eax, 0BFFFh
0x18001ad36  and     cx, ax
0x18001ad39  cmp     cx, 8
0x18001ad3d  jnz     short loc_18001AD58
0x18001ad3f  mov     rax, [rbx+8]
0x18001ad43  mov     rcx, [rdx+rax]; bstrString
0x18001ad47  test    rcx, rcx
0x18001ad4a  jz      loc_18001ADDF
0x18001ad50  call    cs:__imp_SysFreeString
0x18001ad56  jmp     short loc_18001ADB8
0x18001ad58  mov     eax, 4000h
0x18001ad5d  test    [rbx+54h], ax
0x18001ad61  jz      short loc_18001AD99
0x18001ad63  cmp     dword ptr [rbx+3Ch], 0
0x18001ad67  jnz     short loc_18001AD99
0x18001ad69  mov     r8d, 80h
0x18001ad6f  movzx   eax, cx
0x18001ad72  sub     ax, r8w
0x18001ad76  cmp     ax, 2
0x18001ad7a  ja      short loc_18001AD99
0x18001ad7c  mov     rax, [rbx+8]
0x18001ad80  mov     rcx, [rdx+rax]; pv
0x18001ad84  test    rcx, rcx
0x18001ad87  jz      short loc_18001ADDF
0x18001ad89  call    cs:__imp_CoTaskMemFree
0x18001ad8f  mov     rcx, [rbx+8]
0x18001ad93  mov     rax, [rsi+58h]
0x18001ad97  jmp     short loc_18001ADC0
0x18001ad99  cmp     cx, 0Dh
0x18001ad9d  jnz     short loc_18001ADCA
0x18001ad9f  mov     rax, [rbx+8]
0x18001ada3  mov     rcx, [rdx+rax]
0x18001ada7  test    rcx, rcx
0x18001adaa  jz      short loc_18001ADDF
0x18001adac  mov     rax, [rcx]
0x18001adaf  mov     rax, [rax+10h]
0x18001adb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adb8  mov     rcx, [rsi+58h]
0x18001adbc  mov     rax, [rbx+8]
0x18001adc0  mov     qword ptr [rcx+rax], 0
0x18001adc8  jmp     short loc_18001ADDF
0x18001adca  cmp     cx, 0Ch
0x18001adce  jnz     short loc_18001ADDF
0x18001add0  mov     rcx, [rbx+8]
0x18001add4  add     rcx, rdx; pvarg
0x18001add7  jz      short loc_18001ADDF
0x18001add9  call    cs:__imp_VariantClear
0x18001addf  inc     edi
0x18001ade1  add     rbx, 58h ; 'X'
0x18001ade5  cmp     edi, ebp
0x18001ade7  jb      loc_18001AD18
0x18001aded  add     rsp, 28h
0x18001adf1  pop     rdi
0x18001adf2  pop     rsi
0x18001adf3  pop     rbp
0x18001adf4  pop     rbx
0x18001adf5  retn
```
