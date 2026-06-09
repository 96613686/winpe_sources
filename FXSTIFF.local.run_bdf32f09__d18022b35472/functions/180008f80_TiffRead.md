# TiffRead

- ea: `0x180008f80`
- end: `0x180009068`
- name: `TiffRead`
- size: `232`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800044f0`
- `0x180006530`

## callees

- `0x180001da8`
- `0x18000212c`
- `0x1800025e0`
- `0x180002b30`
- `0x180008f80`
- `0x180017bc2`
- `0x180017bce`

## pseudocode

```c
__int64 __fastcall TiffRead(__int64 a1, void *a2, unsigned int a3)
{
  unsigned __int64 v7; // rcx
  unsigned int v8; // eax

  switch ( *(_DWORD *)(a1 + 852) )
  {
    case 1:
      if ( !(unsigned int)Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline()
        || *(_DWORD *)(a1 + 1564) )
      {
        v7 = *(unsigned int *)(a1 + 1568) * ((unsigned __int64)*(unsigned int *)(a1 + 1564) >> 3);
        if ( v7 <= 0xFFFFFFFF && a3 >= (unsigned int)v7 )
        {
          v8 = *(_DWORD *)(a1 + 1552);
          if ( a3 >= v8 )
          {
            *(_DWORD *)(a1 + 848) = v8 / (*(_DWORD *)(a1 + 1564) >> 3);
            memset_0(a2, 0, (unsigned int)v7);
            memcpy_0(a2, *(const void **)(a1 + 1536), *(unsigned int *)(a1 + 1552));
            return 1;
          }
        }
      }
      break;
    case 2:
      return DecodeMHFaxData(a1);
    case 3:
      return DecodeMRFaxData();
    case 4:
      return DecodeMMRFaxData();
  }
  return 0;
}

```

## disassembly

```asm
0x180008f80  mov     [rsp+arg_0], rbx
0x180008f85  mov     [rsp+arg_8], rsi
0x180008f8a  push    rdi
0x180008f8b  sub     rsp, 30h
0x180008f8f  mov     r10d, [rcx+354h]
0x180008f96  mov     edi, r8d
0x180008f99  mov     rsi, rdx
0x180008f9c  mov     rbx, rcx
0x180008f9f  sub     r10d, 1
0x180008fa3  jz      short loc_180008FDB
0x180008fa5  sub     r10d, 1
0x180008fa9  jz      short loc_180008FCF
0x180008fab  sub     r10d, 1
0x180008faf  jz      short loc_180008FC5
0x180008fb1  cmp     r10d, 1
0x180008fb5  jnz     loc_180009056
0x180008fbb  call    DecodeMMRFaxData
0x180008fc0  jmp     loc_180009058
0x180008fc5  call    DecodeMRFaxData
0x180008fca  jmp     loc_180009058
0x180008fcf  mov     [rsp+38h+var_18], r9d
0x180008fd4  call    DecodeMHFaxData
0x180008fd9  jmp     short loc_180009058
0x180008fdb  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x180008fe0  test    eax, eax
0x180008fe2  jz      short loc_180008FED
0x180008fe4  cmp     dword ptr [rbx+61Ch], 0
0x180008feb  jz      short loc_180009056
0x180008fed  mov     eax, [rbx+620h]
0x180008ff3  mov     r8d, [rbx+61Ch]
0x180008ffa  mov     ecx, r8d
0x180008ffd  shr     rcx, 3
0x180009001  imul    rcx, rax
0x180009005  mov     eax, 0FFFFFFFFh
0x18000900a  cmp     rcx, rax
0x18000900d  ja      short loc_180009056
0x18000900f  cmp     edi, ecx
0x180009011  jb      short loc_180009056
0x180009013  mov     eax, [rbx+610h]
0x180009019  cmp     edi, eax
0x18000901b  jb      short loc_180009056
0x18000901d  shr     r8d, 3
0x180009021  xor     edx, edx
0x180009023  div     r8d
0x180009026  mov     r8d, ecx; Size
0x180009029  xor     edx, edx; Val
0x18000902b  mov     rcx, rsi; void *
0x18000902e  mov     [rbx+350h], eax
0x180009034  call    memset_0
0x180009039  mov     r8d, [rbx+610h]; Size
0x180009040  mov     rcx, rsi; void *
0x180009043  mov     rdx, [rbx+600h]; Src
0x18000904a  call    memcpy_0
0x18000904f  mov     eax, 1
0x180009054  jmp     short loc_180009058
0x180009056  xor     eax, eax
0x180009058  mov     rbx, [rsp+38h+arg_0]
0x18000905d  mov     rsi, [rsp+38h+arg_8]
0x180009062  add     rsp, 30h
0x180009066  pop     rdi
0x180009067  retn
```
