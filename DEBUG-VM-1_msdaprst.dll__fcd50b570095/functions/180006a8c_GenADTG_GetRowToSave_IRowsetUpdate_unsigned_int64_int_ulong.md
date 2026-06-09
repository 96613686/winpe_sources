# GenADTG::GetRowToSave(IRowsetUpdate *,unsigned __int64,int,ulong)

- ea: `0x180006a8c`
- end: `0x180006c39`
- name: `?GetRowToSave@GenADTG@@QEAAXPEAUIRowsetUpdate@@_KHK@Z`
- size: `429`
- prototype: `void __fastcall(GenADTG *__hidden this, struct IRowsetUpdate *, unsigned __int64, int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180008c10`

## callees

- `0x180006a8c`
- `0x18001a6c8`
- `0x18002cd54`
- `0x180030010`

## pseudocode

```c
void __fastcall GenADTG::GetRowToSave(GenADTG *this, struct IRowsetUpdate *a2, __int64 a3, int a4, unsigned int a5)
{
  int v5; // ebp
  __int64 i; // rsi
  __int64 v11; // r8
  int v12; // eax
  int v13; // ebx
  unsigned int j; // r8d
  unsigned int v15; // ecx
  int v16; // eax

  v5 = 0;
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 20); i = (unsigned int)(i + 1) )
  {
    v11 = *(_QWORD *)(*((_QWORD *)this + 9) + 8 * i);
    if ( a4 )
      v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(**((_QWORD **)this + 3) + 32LL))(
              *((_QWORD *)this + 3),
              a3,
              v11,
              *((_QWORD *)this + 11));
    else
      v12 = ((__int64 (__fastcall *)(struct IRowsetUpdate *, __int64, __int64, _QWORD))a2->lpVtbl->GetOriginalData)(
              a2,
              a3,
              v11,
              *((_QWORD *)this + 12));
    v13 = v12;
    if ( v12 == -2147217887 || v12 == 265946 )
    {
      v5 = 1;
    }
    else if ( v12 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180048568[0] )
          bidTraceW(off_1800481C0[0], 1836032, off_180048568[0], (unsigned int)v12, 1793);
      }
      ThrowHR(v13);
    }
  }
  if ( v5 )
  {
    for ( j = 0; j < *((unsigned __int16 *)this + 32); ++j )
    {
      v15 = *(_DWORD *)(*(_QWORD *)(88LL * j + *((_QWORD *)this + 7) + 24) + *((_QWORD *)this + 11));
      if ( v15 <= 0xD )
      {
        v16 = 8217;
        if ( _bittest(&v16, v15) )
          continue;
      }
      if ( v15 != 8 )
      {
        if ( v15 == 2 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048560[0] )
            bidTraceW(off_1800481C0[0], 1857536, off_180048560[0], 2147749383LL, 1814);
          ThrowHR(-2147217913);
        }
LABEL_28:
        if ( (bidGblFlags & 2) != 0 && off_180048558[0] )
          bidTraceW(off_1800481C0[0], 1859584, off_180048558[0], 2147749409LL, 1816);
        ThrowHR(-2147217887);
      }
      if ( a5 != 1 )
        goto LABEL_28;
    }
  }
}

```

## disassembly

```asm
0x180006a8c  push    rbx
0x180006a8e  push    rbp
0x180006a8f  push    rsi
0x180006a90  push    rdi
0x180006a91  push    r12
0x180006a93  push    r14
0x180006a95  push    r15
0x180006a97  sub     rsp, 30h
0x180006a9b  xor     ebp, ebp
0x180006a9d  mov     r14d, r9d
0x180006aa0  xor     esi, esi
0x180006aa2  mov     r15, r8
0x180006aa5  mov     r12, rdx
0x180006aa8  mov     rdi, rcx
0x180006aab  cmp     esi, [rdi+50h]
0x180006aae  jnb     loc_180006B48
0x180006ab4  mov     r8, [rdi+48h]
0x180006ab8  mov     rdx, r15
0x180006abb  mov     r8, [r8+rsi*8]
0x180006abf  test    r14d, r14d
0x180006ac2  jz      short loc_180006AD5
0x180006ac4  mov     rcx, [rdi+18h]
0x180006ac8  mov     r9, [rdi+58h]
0x180006acc  mov     rax, [rcx]
0x180006acf  mov     rax, [rax+20h]
0x180006ad3  jmp     short loc_180006AE4
0x180006ad5  mov     rax, [r12]
0x180006ad9  mov     rcx, r12
0x180006adc  mov     r9, [rdi+60h]
0x180006ae0  mov     rax, [rax+30h]
0x180006ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ae9  mov     ebx, eax
0x180006aeb  cmp     eax, 80040E21h
0x180006af0  jz      short loc_180006AF9
0x180006af2  cmp     eax, 40EDAh
0x180006af7  jnz     short loc_180006B00
0x180006af9  mov     ebp, 1
0x180006afe  jmp     short loc_180006B04
0x180006b00  test    ebx, ebx
0x180006b02  js      short loc_180006B08
0x180006b04  inc     esi
0x180006b06  jmp     short loc_180006AAB
0x180006b08  test    byte ptr cs:_bidGblFlags, 2
0x180006b0f  jz      short loc_180006B40
0x180006b11  mov     rax, cs:off_180048568; "<GenADTG::GetRowToSave|ADO|ERR>  HRESUL"...
0x180006b18  test    rax, rax
0x180006b1b  jz      short loc_180006B40
0x180006b1d  mov     r8, cs:off_180048568; "<GenADTG::GetRowToSave|ADO|ERR>  HRESUL"...
0x180006b24  mov     r9d, ebx
0x180006b27  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006b2e  mov     edx, 1C0400h
0x180006b33  mov     [rsp+68h+var_48], 701h
0x180006b3b  call    _bidTraceW
0x180006b40  mov     ecx, ebx; int
0x180006b42  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006b48  test    ebp, ebp
0x180006b4a  jz      loc_180006C2A
0x180006b50  movzx   r9d, word ptr [rdi+40h]
0x180006b55  xor     r8d, r8d
0x180006b58  cmp     r8d, r9d
0x180006b5b  jnb     loc_180006C2A
0x180006b61  mov     eax, r8d
0x180006b64  imul    rcx, rax, 58h ; 'X'
0x180006b68  mov     rax, [rdi+38h]
0x180006b6c  mov     rdx, [rcx+rax+18h]
0x180006b71  mov     rax, [rdi+58h]
0x180006b75  mov     ecx, [rdx+rax]
0x180006b78  cmp     ecx, 0Dh
0x180006b7b  ja      short loc_180006B87
0x180006b7d  mov     eax, 2019h
0x180006b82  bt      eax, ecx
0x180006b85  jb      short loc_180006B96
0x180006b87  cmp     ecx, 8
0x180006b8a  jnz     short loc_180006B9B
0x180006b8c  cmp     [rsp+68h+arg_20], 1
0x180006b94  jnz     short loc_180006BE4
0x180006b96  inc     r8d
0x180006b99  jmp     short loc_180006B58
0x180006b9b  cmp     ecx, 2
0x180006b9e  jnz     short loc_180006BE4
0x180006ba0  test    byte ptr cs:_bidGblFlags, cl
0x180006ba6  mov     ebx, 80040E07h
0x180006bab  jz      short loc_180006BDC
0x180006bad  mov     rax, cs:off_180048560; "<GenADTG::GetRowToSave|ADO|ERR>  HRESUL"...
0x180006bb4  test    rax, rax
0x180006bb7  jz      short loc_180006BDC
0x180006bb9  mov     r8, cs:off_180048560; "<GenADTG::GetRowToSave|ADO|ERR>  HRESUL"...
0x180006bc0  mov     r9d, ebx
0x180006bc3  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006bca  mov     edx, 1C5800h
0x180006bcf  mov     [rsp+68h+var_48], 716h
0x180006bd7  call    _bidTraceW
0x180006bdc  mov     ecx, ebx; int
0x180006bde  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006be4  test    byte ptr cs:_bidGblFlags, 2
0x180006beb  jz      short loc_180006C1F
0x180006bed  mov     rax, cs:off_180048558; "<GenADTG::GetRowToSave|ADO|ERR>  HRESUL"...
0x180006bf4  test    rax, rax
0x180006bf7  jz      short loc_180006C1F
0x180006bf9  mov     r8, cs:off_180048558; "<GenADTG::GetRowToSave|ADO|ERR>  HRESUL"...
0x180006c00  mov     r9d, 80040E21h
0x180006c06  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006c0d  mov     edx, 1C6000h
0x180006c12  mov     [rsp+68h+var_48], 718h
0x180006c1a  call    _bidTraceW
0x180006c1f  mov     ecx, 80040E21h; int
0x180006c24  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006c2a  add     rsp, 30h
0x180006c2e  pop     r15
0x180006c30  pop     r14
0x180006c32  pop     r12
0x180006c34  pop     rdi
0x180006c35  pop     rsi
0x180006c36  pop     rbp
0x180006c37  pop     rbx
0x180006c38  retn
```
