# TiffRead

- ea: `0x1800093d0`
- end: `0x1800094b9`
- name: `TiffRead`
- size: `233`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004540`
- `0x1800066d0`

## callees

- `0x180001dc8`
- `0x18000214c`
- `0x180002600`
- `0x180002b54`
- `0x1800093d0`
- `0x180018992`
- `0x18001899e`

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
0x1800093d0  mov     [rsp+arg_0], rbx
0x1800093d5  mov     [rsp+arg_8], rsi
0x1800093da  push    rdi
0x1800093db  sub     rsp, 30h
0x1800093df  mov     r10d, [rcx+354h]
0x1800093e6  mov     edi, r8d
0x1800093e9  mov     rsi, rdx
0x1800093ec  mov     rbx, rcx
0x1800093ef  sub     r10d, 1
0x1800093f3  jz      short loc_18000942B
0x1800093f5  sub     r10d, 1
0x1800093f9  jz      short loc_18000941F
0x1800093fb  sub     r10d, 1
0x1800093ff  jz      short loc_180009415
0x180009401  cmp     r10d, 1
0x180009405  jnz     loc_1800094A6
0x18000940b  call    DecodeMMRFaxData
0x180009410  jmp     loc_1800094A8
0x180009415  call    DecodeMRFaxData
0x18000941a  jmp     loc_1800094A8
0x18000941f  mov     [rsp+38h+var_18], r9d
0x180009424  call    DecodeMHFaxData
0x180009429  jmp     short loc_1800094A8
0x18000942b  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x180009430  test    eax, eax
0x180009432  jz      short loc_18000943D
0x180009434  cmp     dword ptr [rbx+61Ch], 0
0x18000943b  jz      short loc_1800094A6
0x18000943d  mov     eax, [rbx+620h]
0x180009443  mov     r8d, [rbx+61Ch]
0x18000944a  mov     ecx, r8d
0x18000944d  shr     rcx, 3
0x180009451  imul    rcx, rax
0x180009455  mov     eax, 0FFFFFFFFh
0x18000945a  cmp     rcx, rax
0x18000945d  ja      short loc_1800094A6
0x18000945f  cmp     edi, ecx
0x180009461  jb      short loc_1800094A6
0x180009463  mov     eax, [rbx+610h]
0x180009469  cmp     edi, eax
0x18000946b  jb      short loc_1800094A6
0x18000946d  shr     r8d, 3
0x180009471  xor     edx, edx
0x180009473  div     r8d
0x180009476  mov     r8d, ecx; Size
0x180009479  xor     edx, edx; Val
0x18000947b  mov     rcx, rsi; void *
0x18000947e  mov     [rbx+350h], eax
0x180009484  call    memset_0
0x180009489  mov     r8d, [rbx+610h]; Size
0x180009490  mov     rcx, rsi; void *
0x180009493  mov     rdx, [rbx+600h]; Src
0x18000949a  call    memcpy_0
0x18000949f  mov     eax, 1
0x1800094a4  jmp     short loc_1800094A8
0x1800094a6  xor     eax, eax
0x1800094a8  mov     rbx, [rsp+38h+arg_0]
0x1800094ad  mov     rsi, [rsp+38h+arg_8]
0x1800094b2  add     rsp, 30h
0x1800094b6  pop     rdi
0x1800094b7  retn
```
