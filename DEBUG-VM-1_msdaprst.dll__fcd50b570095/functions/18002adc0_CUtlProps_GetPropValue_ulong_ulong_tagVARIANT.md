# CUtlProps::GetPropValue(ulong,ulong,tagVARIANT *)

- ea: `0x18002adc0`
- end: `0x18002ae91`
- name: `?GetPropValue@CUtlProps@@QEAAHKKPEAUtagVARIANT@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(CUtlProps *__hidden this, unsigned int, unsigned int, struct tagVARIANT *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a77c`
- `0x18001a7d4`
- `0x18001b768`
- `0x18002bb0c`

## callees

- `0x18002adc0`
- `0x18002bad8`
- `0x18002cd54`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18002ae7f`
- `OLEAUT32!__imp_VariantCopy` at `0x18002ae7f`

## pseudocode

```c
__int64 __fastcall CUtlProps::GetPropValue(CUtlProps *this, __int64 a2, __int64 a3, struct tagVARIANT *a4)
{
  unsigned int v5; // edi
  __int64 result; // rax
  __int64 v8; // rdx
  unsigned int UPropValIndex; // eax
  HRESULT v10; // eax
  int v11; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v12; // [rsp+48h] [rbp+10h] BYREF

  v12 = 0;
  v11 = 0;
  v5 = a3;
  result = (*(__int64 (__fastcall **)(CUtlProps *, _QWORD, __int64, unsigned int *))(*(_QWORD *)this + 16LL))(
             this,
             0,
             a3,
             &v12);
  if ( (_DWORD)result )
  {
    v8 = *(_QWORD *)(*((_QWORD *)this + 2) + 16LL);
    if ( (*(_DWORD *)(v8 + 24LL * v12 + 8) & 0x400) != 0 || (*(_BYTE *)(v8 + 24LL * v12 + 12) & 1) != 0 )
    {
      UPropValIndex = CUtlProps::GetUPropValIndex(this, 0, v5);
      v10 = VariantCopy(
              a4,
              (const VARIANTARG *)(*(_QWORD *)(*((_QWORD *)this + 3) + 16LL) + 16LL + 48LL * UPropValIndex));
      if ( v10 < 0 )
        ThrowHR(v10);
    }
    else
    {
      (*(void (__fastcall **)(CUtlProps *, _QWORD, _QWORD, int *, struct tagVARIANT *))(*(_QWORD *)this + 40LL))(
        this,
        0,
        v5,
        &v11,
        a4);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18002adc0  mov     rax, rsp
0x18002adc3  mov     [rax+18h], rbx
0x18002adc7  mov     [rax+20h], rsi
0x18002adcb  mov     [rax+10h], edx
0x18002adce  push    rdi
0x18002adcf  sub     rsp, 30h
0x18002add3  mov     dword ptr [rax+10h], 0
0x18002adda  mov     rsi, r9
0x18002addd  mov     dword ptr [rax+8], 0
0x18002ade4  lea     r9, [rsp+38h+arg_8]
0x18002ade9  mov     rax, [rcx]
0x18002adec  xor     edx, edx
0x18002adee  mov     edi, r8d
0x18002adf1  mov     rbx, rcx
0x18002adf4  mov     rax, [rax+10h]
0x18002adf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adfd  test    eax, eax
0x18002adff  jz      short loc_18002AE45
0x18002ae01  mov     eax, [rsp+38h+arg_8]
0x18002ae05  lea     rcx, [rax+rax*2]
0x18002ae09  mov     rax, [rbx+10h]
0x18002ae0d  mov     rdx, [rax+10h]
0x18002ae11  test    dword ptr [rdx+rcx*8+8], 400h
0x18002ae19  jnz     short loc_18002AE55
0x18002ae1b  test    byte ptr [rdx+rcx*8+0Ch], 1
0x18002ae20  jnz     short loc_18002AE55
0x18002ae22  mov     rax, [rbx]
0x18002ae25  lea     r9, [rsp+38h+arg_0]
0x18002ae2a  mov     r8d, edi
0x18002ae2d  mov     [rsp+38h+var_18], rsi
0x18002ae32  xor     edx, edx
0x18002ae34  mov     rcx, rbx
0x18002ae37  mov     rax, [rax+28h]
0x18002ae3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae40  mov     eax, 1
0x18002ae45  mov     rbx, [rsp+38h+arg_10]
0x18002ae4a  mov     rsi, [rsp+38h+arg_18]
0x18002ae4f  add     rsp, 30h
0x18002ae53  pop     rdi
0x18002ae54  retn
0x18002ae55  mov     r8d, edi; unsigned int
0x18002ae58  xor     edx, edx; unsigned int
0x18002ae5a  mov     rcx, rbx; this
0x18002ae5d  call    ?GetUPropValIndex@CUtlProps@@QEAAKKK@Z; CUtlProps::GetUPropValIndex(ulong,ulong)
0x18002ae62  mov     r8d, eax
0x18002ae65  mov     rax, [rbx+18h]
0x18002ae69  lea     rdx, [r8+r8*2]
0x18002ae6d  mov     rcx, [rax+10h]
0x18002ae71  add     rcx, 10h
0x18002ae75  shl     rdx, 4
0x18002ae79  add     rdx, rcx; pvargSrc
0x18002ae7c  mov     rcx, rsi; pvargDest
0x18002ae7f  call    cs:__imp_VariantCopy
0x18002ae85  test    eax, eax
0x18002ae87  jns     short loc_18002AE40
0x18002ae89  mov     ecx, eax; int
0x18002ae8b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
