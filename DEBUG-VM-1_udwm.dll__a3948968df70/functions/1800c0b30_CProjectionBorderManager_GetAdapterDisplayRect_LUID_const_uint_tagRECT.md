# CProjectionBorderManager::_GetAdapterDisplayRect(_LUID const &,uint,tagRECT *)

- ea: `0x1800c0b30`
- end: `0x1800c0d09`
- name: `?_GetAdapterDisplayRect@CProjectionBorderManager@@AEAAJAEBU_LUID@@IPEAUtagRECT@@@Z`
- size: `473`
- prototype: `__int64 __fastcall(CProjectionBorderManager *__hidden this, const struct _LUID *, unsigned int, struct tagRECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1800c06b0`

## callees

- `0x180017658`
- `0x18001f43c`
- `0x180083a34`
- `0x1800c0614`
- `0x1800c0b30`

## import_xrefs

- `USER32!GetDisplayConfigBufferSizes` at `0x1800c0b78`
- `USER32!GetDisplayConfigBufferSizes` at `0x1800c0b78`
- `USER32!QueryDisplayConfig` at `0x1800c0c14`
- `USER32!QueryDisplayConfig` at `0x1800c0c14`

## pseudocode

```c
__int64 __fastcall CProjectionBorderManager::_GetAdapterDisplayRect(
        CProjectionBorderManager *this,
        const struct _LUID *a2,
        int a3,
        struct tagRECT *a4)
{
  LONG DisplayConfigBufferSizes; // eax
  unsigned int v8; // esi
  DISPLAYCONFIG_PATH_INFO *v9; // rbp
  DISPLAYCONFIG_MODE_INFO *modeInfoArray; // rax
  DISPLAYCONFIG_MODE_INFO *v11; // rbx
  signed __int64 i; // rdx
  LONG v13; // eax
  signed int v14; // edi
  __int64 v15; // rcx
  LONG v16; // r8d
  LONG v17; // r9d
  int v18; // eax
  const struct std::nothrow_t *v19; // rdx
  UINT32 numModeInfoArrayElements[4]; // [rsp+30h] [rbp-38h] BYREF
  UINT32 numPathArrayElements; // [rsp+70h] [rbp+8h] BYREF
  int v23; // [rsp+74h] [rbp+Ch]

  v23 = HIDWORD(this);
  numPathArrayElements = 0;
  numModeInfoArrayElements[0] = 0;
  *a4 = 0;
  DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(1u, &numPathArrayElements, numModeInfoArrayElements);
  v8 = DisplayConfigBufferSizes;
  if ( DisplayConfigBufferSizes < 0 )
  {
    v9 = 0;
    v11 = 0;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, DisplayConfigBufferSizes, 0x16u, 0);
  }
  else
  {
    v9 = (DISPLAYCONFIG_PATH_INFO *)operator new(saturated_mul(numPathArrayElements, 0x48u));
    modeInfoArray = (DISPLAYCONFIG_MODE_INFO *)operator new(saturated_mul(numModeInfoArrayElements[0], 0x40u));
    v11 = modeInfoArray;
    if ( v9 )
    {
      if ( modeInfoArray )
      {
        v13 = QueryDisplayConfig(1u, &numPathArrayElements, v9, numModeInfoArrayElements, modeInfoArray, 0);
        v14 = v13;
        if ( v13 > 0 )
          v14 = (unsigned __int16)v13 | 0x80070000;
        if ( v14 < 0 )
        {
          WindowFrameLoggingTelemetry::ScreenDuplicationFailedToGetDisplayConfig();
          v8 = v14;
        }
        else
        {
          for ( i = 0; (unsigned int)i < numPathArrayElements; i = (unsigned int)(i + 1) )
          {
            v15 = i;
            if ( v9[i].sourceInfo.adapterId.LowPart == a2->LowPart
              && v9[i].sourceInfo.adapterId.HighPart == a2->HighPart
              && v9[i].sourceInfo.id == a3 )
            {
              _mm_lfence();
              i = (unsigned __int64)v9[i].sourceInfo.modeInfoIdx << 6;
              v16 = *(LONG *)((char *)&v11->sourceMode.position.x + i);
              a4->left = v16;
              v17 = *(LONG *)((char *)&v11->sourceMode.position.y + i);
              a4->top = v17;
              if ( ((v9[v15].targetInfo.rotation - 2) & 0xFFFFFFFD) != 0 )
              {
                a4->right = v16 + *(UINT32 *)((char *)&v11->sourceMode.width + i);
                v18 = *(LONG *)((char *)&v11->desktopImageInfo.PathSourceSize.y + i);
              }
              else
              {
                a4->right = v16 + *(UINT32 *)((char *)&v11->sourceMode.height + i);
                v18 = *(LONG *)((char *)&v11->desktopImageInfo.PathSourceSize.x + i);
              }
              a4->bottom = v17 + v18;
              v8 = 0;
              break;
            }
          }
        }
      }
      else
      {
        v8 = -2147024882;
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x1Bu, 0);
      }
    }
    else
    {
      v8 = -2147024882;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x1Au, 0);
    }
  }
  CDisplayBlackCurtainAnimatedVisual::operator delete(v9, (const struct std::nothrow_t *)i);
  CDisplayBlackCurtainAnimatedVisual::operator delete(v11, v19);
  return v8;
}

```

## disassembly

```asm
0x1800c0b30  mov     rax, rsp
0x1800c0b33  mov     [rax+10h], rbx
0x1800c0b37  mov     [rax+18h], rbp
0x1800c0b3b  mov     [rax+8], rcx
0x1800c0b3f  push    rsi
0x1800c0b40  push    rdi
0x1800c0b41  push    r12
0x1800c0b43  push    r14
0x1800c0b45  push    r15
0x1800c0b47  sub     rsp, 40h
0x1800c0b4b  mov     r12d, r8d
0x1800c0b4e  mov     dword ptr [rax+8], 0
0x1800c0b55  mov     r15, rdx
0x1800c0b58  mov     dword ptr [rax-38h], 0
0x1800c0b5f  xorps   xmm0, xmm0
0x1800c0b62  lea     r8, [rax-38h]; numModeInfoArrayElements
0x1800c0b66  mov     edi, 1
0x1800c0b6b  lea     rdx, [rax+8]; numPathArrayElements
0x1800c0b6f  mov     ecx, edi; flags
0x1800c0b71  mov     r14, r9
0x1800c0b74  movups  xmmword ptr [r9], xmm0
0x1800c0b78  call    cs:__imp_GetDisplayConfigBufferSizes
0x1800c0b7e  mov     esi, eax
0x1800c0b80  test    eax, eax
0x1800c0b82  js      loc_1800C0CBD
0x1800c0b88  mov     ecx, [rsp+68h+numPathArrayElements]
0x1800c0b8c  lea     eax, [rdi+47h]
0x1800c0b8f  mul     rcx
0x1800c0b92  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800c0b99  cmovb   rax, rbx
0x1800c0b9d  mov     rcx, rax; unsigned __int64
0x1800c0ba0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c0ba5  mov     ecx, [rsp+68h+numModeInfoArrayElements]
0x1800c0ba9  mov     rbp, rax
0x1800c0bac  lea     eax, [rdi+3Fh]
0x1800c0baf  mul     rcx
0x1800c0bb2  cmovb   rax, rbx
0x1800c0bb6  mov     rcx, rax; unsigned __int64
0x1800c0bb9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c0bbe  mov     [rsp+68h+currentTopologyId], 0; currentTopologyId
0x1800c0bc7  mov     rbx, rax
0x1800c0bca  test    rbp, rbp
0x1800c0bcd  jnz     short loc_1800C0BE5
0x1800c0bcf  mov     r9d, 8007000Eh
0x1800c0bd5  mov     dword ptr [rsp+68h+modeInfoArray], 1Ah
0x1800c0bdd  mov     esi, r9d
0x1800c0be0  jmp     loc_1800C0CD1
0x1800c0be5  test    rbx, rbx
0x1800c0be8  jnz     short loc_1800C0C00
0x1800c0bea  mov     r9d, 8007000Eh
0x1800c0bf0  mov     dword ptr [rsp+68h+modeInfoArray], 1Bh
0x1800c0bf8  mov     esi, r9d
0x1800c0bfb  jmp     loc_1800C0CD1
0x1800c0c00  lea     r9, [rsp+68h+numModeInfoArrayElements]; numModeInfoArrayElements
0x1800c0c05  mov     [rsp+68h+modeInfoArray], rbx; modeInfoArray
0x1800c0c0a  mov     r8, rbp; pathArray
0x1800c0c0d  lea     rdx, [rsp+68h+numPathArrayElements]; numPathArrayElements
0x1800c0c12  mov     ecx, edi; flags
0x1800c0c14  call    cs:__imp_QueryDisplayConfig
0x1800c0c1a  mov     edi, eax
0x1800c0c1c  test    eax, eax
0x1800c0c1e  jle     short loc_1800C0C29
0x1800c0c20  movzx   edi, ax
0x1800c0c23  or      edi, 80070000h
0x1800c0c29  test    edi, edi
0x1800c0c2b  js      loc_1800C0CB4
0x1800c0c31  xor     edx, edx
0x1800c0c33  cmp     edx, [rsp+68h+numPathArrayElements]
0x1800c0c37  jnb     loc_1800C0CDE
0x1800c0c3d  mov     eax, [r15]
0x1800c0c40  lea     rcx, [rdx+rdx*8]
0x1800c0c44  cmp     [rbp+rcx*8+0], eax
0x1800c0c48  jnz     short loc_1800C0C5B
0x1800c0c4a  mov     eax, [r15+4]
0x1800c0c4e  cmp     [rbp+rcx*8+4], eax
0x1800c0c52  jnz     short loc_1800C0C5B
0x1800c0c54  cmp     [rbp+rcx*8+8], r12d
0x1800c0c59  jz      short loc_1800C0C5F
0x1800c0c5b  inc     edx
0x1800c0c5d  jmp     short loc_1800C0C33
0x1800c0c5f  lfence
0x1800c0c62  mov     edx, [rbp+rcx*8+0Ch]
0x1800c0c66  shl     rdx, 6
0x1800c0c6a  mov     r8d, [rdx+rbx+1Ch]
0x1800c0c6f  mov     [r14], r8d
0x1800c0c72  mov     r9d, [rdx+rbx+20h]
0x1800c0c77  mov     [r14+4], r9d
0x1800c0c7b  mov     eax, [rbp+rcx*8+28h]
0x1800c0c7f  sub     eax, 2
0x1800c0c82  test    eax, 0FFFFFFFDh
0x1800c0c87  jz      short loc_1800C0C9A
0x1800c0c89  mov     ecx, [rdx+rbx+10h]
0x1800c0c8d  add     ecx, r8d
0x1800c0c90  mov     [r14+8], ecx
0x1800c0c94  mov     eax, [rdx+rbx+14h]
0x1800c0c98  jmp     short loc_1800C0CA9
0x1800c0c9a  mov     ecx, [rdx+rbx+14h]
0x1800c0c9e  add     ecx, r8d
0x1800c0ca1  mov     [r14+8], ecx
0x1800c0ca5  mov     eax, [rdx+rbx+10h]
0x1800c0ca9  add     eax, r9d
0x1800c0cac  mov     [r14+0Ch], eax
0x1800c0cb0  xor     esi, esi
0x1800c0cb2  jmp     short loc_1800C0CDE
0x1800c0cb4  call    ?ScreenDuplicationFailedToGetDisplayConfig@WindowFrameLoggingTelemetry@@SAXXZ; WindowFrameLoggingTelemetry::ScreenDuplicationFailedToGetDisplayConfig(void)
0x1800c0cb9  mov     esi, edi
0x1800c0cbb  jmp     short loc_1800C0CDE
0x1800c0cbd  xor     ebp, ebp
0x1800c0cbf  mov     r9d, eax; int
0x1800c0cc2  xor     ebx, ebx
0x1800c0cc4  mov     [rsp+68h+currentTopologyId], rbx; void *
0x1800c0cc9  mov     dword ptr [rsp+68h+modeInfoArray], 16h; unsigned int
0x1800c0cd1  xor     edx, edx; int *
0x1800c0cd3  xor     r8d, r8d; unsigned int
0x1800c0cd6  lea     ecx, [rdx+14h]; unsigned int
0x1800c0cd9  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800c0cde  mov     rcx, rbp; void *
0x1800c0ce1  call    ??3CDisplayBlackCurtainAnimatedVisual@@KAXPEAXAEBUnothrow_t@std@@@Z; CDisplayBlackCurtainAnimatedVisual::operator delete(void *,std::nothrow_t const &)
0x1800c0ce6  mov     rcx, rbx; void *
0x1800c0ce9  call    ??3CDisplayBlackCurtainAnimatedVisual@@KAXPEAXAEBUnothrow_t@std@@@Z; CDisplayBlackCurtainAnimatedVisual::operator delete(void *,std::nothrow_t const &)
0x1800c0cee  lea     r11, [rsp+68h+var_28]
0x1800c0cf3  mov     eax, esi
0x1800c0cf5  mov     rbx, [r11+38h]
0x1800c0cf9  mov     rbp, [r11+40h]
0x1800c0cfd  mov     rsp, r11
0x1800c0d00  pop     r15
0x1800c0d02  pop     r14
0x1800c0d04  pop     r12
0x1800c0d06  pop     rdi
0x1800c0d07  pop     rsi
0x1800c0d08  retn
```
