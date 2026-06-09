# UsacConfig_Parse

- ea: `0x18004afa0`
- end: `0x18004b12d`
- name: `UsacConfig_Parse`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180011da8`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x180012768`
- `0x18004afa0`
- `0x180079784`
- `0x180079890`
- `0x180079960`
- `0x180079f58`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall UsacConfig_Parse(__int64 a1, int *a2, _QWORD *a3)
{
  int v6; // r15d
  int SampleRate; // eax
  __int64 v8; // r8
  int v9; // eax
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // rsi
  __int64 result; // rax
  unsigned int v14; // edi
  __int64 v15; // r8
  __int64 v16; // rcx
  unsigned int v17; // esi
  __int64 (__fastcall *v18)(_QWORD, _QWORD, _QWORD, __int64, _DWORD, _DWORD, _DWORD); // rax

  CDKsyncCache_0(a2);
  v6 = a2[2];
  SampleRate = getSampleRate(a2, a1 + 1231, 5);
  if ( !SampleRate )
    return 1025;
  if ( SampleRate > 96000 )
    return 1025;
  *(_DWORD *)(a1 + 1204) = SampleRate;
  v9 = CDKreadBits(a2, 3, v8);
  if ( (unsigned int)UsacConfig_SetCoreSbrFrameLengthIndex(a1, v9) )
    return 1025;
  v11 = CDKreadBits(a2, 5, v10);
  v12 = v11;
  if ( v11 > 2 || !v11 )
    return 1025;
  *(_BYTE *)(a1 + 1224) = v11;
  result = UsacMpegHDecoderConfig_Parse(a1, a2, a3);
  v14 = result;
  if ( (_DWORD)result )
    return result;
  CDKsyncCache_0(a2);
  if ( a2[2] <= 0 )
    return 257;
  if ( (unsigned int)CDKreadBits(a2, 1, v15) )
  {
    result = configExtension(v16, a2, a3);
  }
  else
  {
    v18 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64, _DWORD, _DWORD, _DWORD))a3[14];
    if ( !v18 )
      goto LABEL_12;
    result = v18(a3[15], 0, 0, 1, 0, 0, *(_DWORD *)(a1 + 1200));
  }
  v14 = result;
  if ( (_DWORD)result )
    return result;
LABEL_12:
  if ( (int)v12 <= 0 || *((char *)qword_1800BA980 + 4 * v12) == *(unsigned __int8 *)(a1 + 3) )
  {
    CDKsyncCache_0(a2);
    v17 = a2[2] - v6;
    if ( !(unsigned int)StoreConfigAsBitstream(a2, v17, a1 + 215) )
    {
      *(_WORD *)(a1 + 728) = (v17 - (v17 >> 31)) ^ ((int)(v17 - (v17 >> 31)) >> 31);
      return v14;
    }
  }
  return 1025;
}

```

## disassembly

```asm
0x18004afa0  push    rbx
0x18004afa2  push    rbp
0x18004afa3  push    rsi
0x18004afa4  push    rdi
0x18004afa5  push    r14
0x18004afa7  push    r15
0x18004afa9  sub     rsp, 48h
0x18004afad  mov     rbp, rcx
0x18004afb0  mov     r14, r8
0x18004afb3  mov     rcx, rdx
0x18004afb6  mov     rbx, rdx
0x18004afb9  call    CDKsyncCache_0
0x18004afbe  mov     r15d, [rbx+8]
0x18004afc2  lea     rdx, [rbp+4CFh]
0x18004afc9  mov     edi, 5
0x18004afce  mov     rcx, rbx
0x18004afd1  mov     r8d, edi
0x18004afd4  call    getSampleRate
0x18004afd9  test    eax, eax
0x18004afdb  jz      loc_18004B11A
0x18004afe1  cmp     eax, 17700h
0x18004afe6  jg      loc_18004B11A
0x18004afec  lea     edx, [rdi-2]
0x18004afef  mov     [rbp+4B4h], eax
0x18004aff5  mov     rcx, rbx
0x18004aff8  call    CDKreadBits
0x18004affd  mov     edx, eax
0x18004afff  mov     rcx, rbp
0x18004b002  call    UsacConfig_SetCoreSbrFrameLengthIndex
0x18004b007  test    eax, eax
0x18004b009  jnz     loc_18004B11A
0x18004b00f  mov     edx, edi
0x18004b011  mov     rcx, rbx
0x18004b014  call    CDKreadBits
0x18004b019  movsxd  rsi, eax
0x18004b01c  cmp     esi, 2
0x18004b01f  jg      loc_18004B11A
0x18004b025  test    eax, eax
0x18004b027  jz      loc_18004B11A
0x18004b02d  mov     r8, r14
0x18004b030  mov     [rbp+4C8h], sil
0x18004b037  mov     rdx, rbx
0x18004b03a  mov     rcx, rbp
0x18004b03d  call    UsacMpegHDecoderConfig_Parse
0x18004b042  mov     edi, eax
0x18004b044  test    eax, eax
0x18004b046  jnz     loc_18004B11F
0x18004b04c  mov     rcx, rbx
0x18004b04f  call    CDKsyncCache_0
0x18004b054  cmp     [rbx+8], edi
0x18004b057  jg      short loc_18004B063
0x18004b059  mov     eax, 101h
0x18004b05e  jmp     loc_18004B11F
0x18004b063  mov     edx, 1
0x18004b068  mov     rcx, rbx
0x18004b06b  call    CDKreadBits
0x18004b070  test    eax, eax
0x18004b072  jz      short loc_18004B0DD
0x18004b074  mov     r8, r14
0x18004b077  mov     rdx, rbx
0x18004b07a  call    configExtension
0x18004b07f  mov     edi, eax
0x18004b081  test    eax, eax
0x18004b083  jnz     loc_18004B11F
0x18004b089  test    esi, esi
0x18004b08b  jle     short loc_18004B0A0
0x18004b08d  movzx   eax, byte ptr [rbp+3]
0x18004b091  lea     rcx, qword_1800BA980
0x18004b098  movsx   ecx, byte ptr [rcx+rsi*4]
0x18004b09c  cmp     ecx, eax
0x18004b09e  jnz     short loc_18004B11A
0x18004b0a0  mov     rcx, rbx
0x18004b0a3  call    CDKsyncCache_0
0x18004b0a8  mov     esi, [rbx+8]
0x18004b0ab  lea     r8, [rbp+0D7h]
0x18004b0b2  sub     esi, r15d
0x18004b0b5  mov     rcx, rbx
0x18004b0b8  mov     edx, esi
0x18004b0ba  call    StoreConfigAsBitstream
0x18004b0bf  test    eax, eax
0x18004b0c1  jnz     short loc_18004B11A
0x18004b0c3  mov     eax, esi
0x18004b0c5  shr     eax, 1Fh
0x18004b0c8  sub     esi, eax
0x18004b0ca  mov     eax, esi
0x18004b0cc  sar     eax, 1Fh
0x18004b0cf  xor     ax, si
0x18004b0d2  mov     [rbp+2D8h], ax
0x18004b0d9  mov     eax, edi
0x18004b0db  jmp     short loc_18004B11F
0x18004b0dd  mov     rax, [r14+70h]
0x18004b0e1  test    rax, rax
0x18004b0e4  jz      short loc_18004B089
0x18004b0e6  mov     ecx, [rbp+4B0h]
0x18004b0ec  mov     r9d, 1
0x18004b0f2  mov     [rsp+78h+var_48], ecx
0x18004b0f6  xor     r8d, r8d
0x18004b0f9  mov     rcx, [r14+78h]
0x18004b0fd  xor     edx, edx
0x18004b0ff  mov     [rsp+78h+var_50], 0
0x18004b107  mov     [rsp+78h+var_58], 0
0x18004b10f  call    cs:__guard_dispatch_icall_fptr
0x18004b115  jmp     loc_18004B07F
0x18004b11a  mov     eax, 401h
0x18004b11f  add     rsp, 48h
0x18004b123  pop     r15
0x18004b125  pop     r14
0x18004b127  pop     rdi
0x18004b128  pop     rsi
0x18004b129  pop     rbp
0x18004b12a  pop     rbx
0x18004b12b  retn
```
