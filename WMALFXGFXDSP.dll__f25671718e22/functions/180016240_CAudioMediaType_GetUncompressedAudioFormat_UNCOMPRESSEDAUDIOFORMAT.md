# CAudioMediaType::GetUncompressedAudioFormat(_UNCOMPRESSEDAUDIOFORMAT *)

- ea: `0x180016240`
- end: `0x18001630e`
- name: `?GetUncompressedAudioFormat@CAudioMediaType@@UEAAJPEAU_UNCOMPRESSEDAUDIOFORMAT@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(CAudioMediaType *__hidden this, struct _UNCOMPRESSEDAUDIOFORMAT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016240`

## pseudocode

```c
__int64 __fastcall CAudioMediaType::GetUncompressedAudioFormat(
        CAudioMediaType *this,
        struct _UNCOMPRESSEDAUDIOFORMAT *a2)
{
  __int64 v2; // r8
  DWORD v3; // eax
  float v4; // xmm1_4

  if ( !a2 )
    return 2147500035LL;
  v2 = *((_QWORD *)this + 2);
  if ( !v2 )
    return 2147500035LL;
  if ( *(_WORD *)v2 == 0xFFFE )
  {
    a2->guidFormatType = *(GUID *)(v2 + 24);
    a2->dwSamplesPerFrame = *(unsigned __int16 *)(v2 + 2);
    a2->dwBytesPerSampleContainer = *(unsigned __int16 *)(v2 + 14) >> 3;
    a2->dwValidBitsPerSample = *(unsigned __int16 *)(v2 + 18);
    a2->fFramesPerSecond = (float)*(int *)(v2 + 4);
    v3 = *(_DWORD *)(v2 + 20);
  }
  else
  {
    a2->guidFormatType = GUID_00000000_0000_0010_8000_00aa00389b71;
    a2->guidFormatType.Data1 = **((unsigned __int16 **)this + 2);
    a2->dwSamplesPerFrame = *(unsigned __int16 *)(*((_QWORD *)this + 2) + 2LL);
    a2->dwBytesPerSampleContainer = *(unsigned __int16 *)(*((_QWORD *)this + 2) + 14LL) >> 3;
    a2->dwValidBitsPerSample = *(unsigned __int16 *)(*((_QWORD *)this + 2) + 14LL);
    v3 = 0;
    a2->fFramesPerSecond = (float)*(int *)(*((_QWORD *)this + 2) + 4LL);
  }
  a2->dwChannelMask = v3;
  v4 = *((float *)this + 6);
  if ( v4 != 0.0 )
    a2->fFramesPerSecond = v4;
  return 0;
}

```

## disassembly

```asm
0x180016240  mov     r9, rcx
0x180016243  test    rdx, rdx
0x180016246  jz      loc_180016308
0x18001624c  mov     r8, [rcx+10h]
0x180016250  test    r8, r8
0x180016253  jz      loc_180016308
0x180016259  mov     eax, 0FFFEh
0x18001625e  cmp     ax, [r8]
0x180016262  jnz     short loc_18001629F
0x180016264  movups  xmm0, xmmword ptr [r8+18h]
0x180016269  movdqu  xmmword ptr [rdx], xmm0
0x18001626d  movzx   eax, word ptr [r8+2]
0x180016272  mov     [rdx+10h], eax
0x180016275  xorps   xmm0, xmm0
0x180016278  movzx   eax, word ptr [r8+0Eh]
0x18001627d  shr     eax, 3
0x180016280  mov     [rdx+14h], eax
0x180016283  movzx   eax, word ptr [r8+12h]
0x180016288  mov     [rdx+18h], eax
0x18001628b  mov     eax, [r8+4]
0x18001628f  cvtsi2ss xmm0, rax
0x180016294  movss   dword ptr [rdx+1Ch], xmm0
0x180016299  mov     eax, [r8+14h]
0x18001629d  jmp     short loc_1800162ED
0x18001629f  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data1
0x1800162a6  movdqu  xmmword ptr [rdx], xmm0
0x1800162aa  mov     rax, [rcx+10h]
0x1800162ae  xorps   xmm0, xmm0
0x1800162b1  movzx   ecx, word ptr [rax]
0x1800162b4  mov     [rdx], ecx
0x1800162b6  mov     rax, [r9+10h]
0x1800162ba  movzx   ecx, word ptr [rax+2]
0x1800162be  mov     [rdx+10h], ecx
0x1800162c1  mov     rax, [r9+10h]
0x1800162c5  movzx   ecx, word ptr [rax+0Eh]
0x1800162c9  shr     ecx, 3
0x1800162cc  mov     [rdx+14h], ecx
0x1800162cf  mov     rax, [r9+10h]
0x1800162d3  movzx   ecx, word ptr [rax+0Eh]
0x1800162d7  mov     [rdx+18h], ecx
0x1800162da  mov     rax, [r9+10h]
0x1800162de  mov     ecx, [rax+4]
0x1800162e1  xor     eax, eax
0x1800162e3  cvtsi2ss xmm0, rcx
0x1800162e8  movss   dword ptr [rdx+1Ch], xmm0
0x1800162ed  mov     [rdx+20h], eax
0x1800162f0  xorps   xmm0, xmm0
0x1800162f3  movss   xmm1, dword ptr [r9+18h]
0x1800162f9  ucomiss xmm0, xmm1
0x1800162fc  jp      short loc_180016300
0x1800162fe  jz      short loc_180016305
0x180016300  movss   dword ptr [rdx+1Ch], xmm1
0x180016305  xor     eax, eax
0x180016307  retn
0x180016308  mov     eax, 80004003h
0x18001630d  retn
```
