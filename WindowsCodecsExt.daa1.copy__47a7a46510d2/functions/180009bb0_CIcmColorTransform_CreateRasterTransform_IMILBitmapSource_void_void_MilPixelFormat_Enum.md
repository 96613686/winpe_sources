# CIcmColorTransform::CreateRasterTransform(IMILBitmapSource *,void *,void *,MilPixelFormat::Enum)

- ea: `0x180009bb0`
- end: `0x180009dd8`
- name: `?CreateRasterTransform@CIcmColorTransform@@UEAAJPEAUIMILBitmapSource@@PEAX1W4Enum@MilPixelFormat@@@Z`
- size: `552`
- prototype: `__int64 __fastcall(__int64, struct IMILBitmapSource *, __int64, __int64, size_t Size)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800058c0`
- `0x1800058e0`
- `0x180005b68`
- `0x180007410`
- `0x180008240`
- `0x180009bb0`
- `0x180009fb4`
- `0x18000a2b8`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009c66`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009c66`

## pseudocode

```c
__int64 __fastcall CIcmColorTransform::CreateRasterTransform(
        __int64 a1,
        struct IMILBitmapSource *a2,
        __int64 a3,
        __int64 a4,
        size_t Size)
{
  int v9; // ebx
  int PixelFormatExtended; // edi
  __int64 v11; // rdx
  __int64 v12; // rcx
  void *v13; // rax
  __int64 v15; // rdi
  _QWORD v16[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v17; // [rsp+80h] [rbp+30h] BYREF

  v9 = _mm_getcsr();
  if ( (v9 & 0xFF80) != 0x1F80 )
  {
    LODWORD(v17) = 8064;
    _mm_setcsr(0x1F80u);
  }
  LODWORD(v17) = 0;
  CMTALock::Enter((CMTALock *)(a1 - 56));
  *(_DWORD *)(a1 + 100) = Size;
  if ( !a2 || !a3 || !a4 )
  {
    PixelFormatExtended = -2147024809;
    goto LABEL_5;
  }
  if ( *(struct IMILBitmapSource **)(a1 + 56) != a2 )
  {
    if ( *(_QWORD *)(a1 + 56) )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 56) + 16LL))(*(_QWORD *)(a1 + 56));
    *(_QWORD *)(a1 + 56) = a2;
    (*(void (__fastcall **)(struct IMILBitmapSource *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  PixelFormatExtended = CIcmColorTransform::GetPixelFormatExtended(
                          (CIcmColorTransform *)(a1 - 72),
                          a2,
                          (enum MilPixelFormat::Enum *)(a1 + 92));
  if ( PixelFormatExtended < 0 )
    goto LABEL_5;
  PixelFormatExtended = CIcmColorTransform::SetupCompatibleTransform((CIcmColorTransform *)(a1 - 72), (int *)&v17);
  if ( PixelFormatExtended < 0 )
    goto LABEL_5;
  if ( (_DWORD)v17 != 1 )
    (***(void (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 56))(*(_QWORD *)(a1 + 56), &IID_IMILBitmap, a1 + 72);
  if ( !ICMModule::EnsureLoaded() )
  {
    PixelFormatExtended = -2003292336;
    goto LABEL_5;
  }
  v17 = 0;
  v16[0] = a3;
  v15 = 0;
  v16[1] = a4;
  if ( ICMModule::EnsureLoaded() )
    v15 = ((__int64 (__fastcall *)(_QWORD *, __int64, __int64 *, __int64, int, _DWORD))ICMModule::s_pfnCreateMultiProfileTransform)(
            v16,
            2,
            &v17,
            2,
            131075,
            0);
  *(_QWORD *)(a1 + 80) = v15;
  if ( !v15 )
  {
    PixelFormatExtended = -2147022885;
    goto LABEL_5;
  }
  PixelFormatExtended = 0;
  *(_DWORD *)(a1 + 104) = 1;
  if ( *(_QWORD *)(a1 + 72) )
    goto LABEL_6;
  v11 = *(unsigned int *)(a1 + 92);
  v12 = *(unsigned int *)(a1 + 136);
  LODWORD(Size) = 0;
  PixelFormatExtended = HrCalcDWordAlignedScanlineStride(v12, v11, &Size);
  if ( PixelFormatExtended < 0 )
    goto LABEL_5;
  v13 = malloc((unsigned int)Size);
  *(_QWORD *)(a1 + 112) = v13;
  if ( !v13 )
    PixelFormatExtended = -2147024882;
  if ( PixelFormatExtended < 0 )
  {
LABEL_5:
    CIcmColorTransform::Free((CIcmColorTransform *)(a1 - 72));
LABEL_6:
    if ( PixelFormatExtended < 0 && g_doStackCaptures )
      DoStackCapture(PixelFormatExtended);
  }
  if ( a1 != 56 )
    CMTALock::Leave((CMTALock *)(a1 - 56));
  if ( (v9 & 0xFF80) != 0x1F80 )
  {
    LODWORD(Size) = v9 & 0xFFFFFFC0;
    _mm_setcsr(v9 & 0xFFFFFFC0);
  }
  return (unsigned int)PixelFormatExtended;
}

```

## disassembly

```asm
0x180009bb0  mov     [rsp-28h+arg_8], rbx
0x180009bb5  mov     [rsp-28h+arg_10], rsi
0x180009bba  push    rbp
0x180009bbb  push    rdi
0x180009bbc  push    r12
0x180009bbe  push    r14
0x180009bc0  push    r15
0x180009bc2  mov     rbp, rsp
0x180009bc5  sub     rsp, 50h
0x180009bc9  mov     r15, r9
0x180009bcc  mov     r12, r8
0x180009bcf  mov     rdi, rdx
0x180009bd2  mov     rsi, rcx
0x180009bd5  stmxcsr dword ptr [rbp+arg_0]
0x180009bd9  mov     ebx, dword ptr [rbp+arg_0]
0x180009bdc  mov     ecx, 1F80h
0x180009be1  mov     eax, ebx
0x180009be3  and     eax, 0FF80h
0x180009be8  cmp     eax, ecx
0x180009bea  jz      short loc_180009BF3
0x180009bec  mov     dword ptr [rbp+arg_0], ecx
0x180009bef  ldmxcsr dword ptr [rbp+arg_0]
0x180009bf3  lea     r14, [rsi-38h]
0x180009bf7  mov     dword ptr [rbp+arg_0], 0
0x180009bfe  mov     rcx, r14; this
0x180009c01  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180009c06  mov     eax, dword ptr [rbp+Size]
0x180009c09  mov     [rsi+64h], eax
0x180009c0c  test    rdi, rdi
0x180009c0f  jnz     loc_180009CBF
0x180009c15  mov     edi, 80070057h
0x180009c1a  lea     rcx, [rsi-48h]; this
0x180009c1e  call    ?Free@CIcmColorTransform@@IEAAXXZ; CIcmColorTransform::Free(void)
0x180009c23  test    edi, edi
0x180009c25  jns     short loc_180009C7F
0x180009c27  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180009c2e  jz      short loc_180009C7F
0x180009c30  mov     ecx, edi; int
0x180009c32  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180009c37  jmp     short loc_180009C7F
0x180009c39  xor     edi, edi
0x180009c3b  mov     dword ptr [rsi+68h], 1
0x180009c42  cmp     [rsi+48h], rdi
0x180009c46  jnz     short loc_180009C23
0x180009c48  mov     edx, [rsi+5Ch]
0x180009c4b  lea     r8, [rbp+Size]
0x180009c4f  mov     ecx, [rsi+88h]
0x180009c55  mov     dword ptr [rbp+Size], edi
0x180009c58  call    ?HrCalcDWordAlignedScanlineStride@@YAJIW4Enum@MilPixelFormat@@AEAI@Z; HrCalcDWordAlignedScanlineStride(uint,MilPixelFormat::Enum,uint &)
0x180009c5d  mov     edi, eax
0x180009c5f  test    eax, eax
0x180009c61  js      short loc_180009C1A
0x180009c63  mov     ecx, dword ptr [rbp+Size]; Size
0x180009c66  call    cs:__imp_malloc
0x180009c6c  test    rax, rax
0x180009c6f  mov     [rsi+70h], rax
0x180009c73  mov     ecx, 8007000Eh
0x180009c78  cmovz   edi, ecx
0x180009c7b  test    edi, edi
0x180009c7d  js      short loc_180009C1A
0x180009c7f  test    r14, r14
0x180009c82  jz      short loc_180009C8C
0x180009c84  mov     rcx, r14; this
0x180009c87  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x180009c8c  mov     eax, ebx
0x180009c8e  and     eax, 0FF80h
0x180009c93  cmp     eax, 1F80h
0x180009c98  jz      short loc_180009CA4
0x180009c9a  and     ebx, 0FFFFFFC0h
0x180009c9d  mov     dword ptr [rbp+Size], ebx
0x180009ca0  ldmxcsr dword ptr [rbp+Size]
0x180009ca4  lea     r11, [rsp+50h+var_s0]
0x180009ca9  mov     eax, edi
0x180009cab  mov     rbx, [r11+38h]
0x180009caf  mov     rsi, [r11+40h]
0x180009cb3  mov     rsp, r11
0x180009cb6  pop     r15
0x180009cb8  pop     r14
0x180009cba  pop     r12
0x180009cbc  pop     rdi
0x180009cbd  pop     rbp
0x180009cbe  retn
0x180009cbf  test    r12, r12
0x180009cc2  jz      loc_180009C15
0x180009cc8  test    r15, r15
0x180009ccb  jz      loc_180009C15
0x180009cd1  cmp     [rsi+38h], rdi
0x180009cd5  jz      short loc_180009CF5
0x180009cd7  cmp     qword ptr [rsi+38h], 0
0x180009cdc  jnz     loc_180009DBF
0x180009ce2  mov     [rsi+38h], rdi
0x180009ce6  mov     rcx, rdi
0x180009ce9  mov     rax, [rdi]
0x180009cec  mov     rax, [rax+8]
0x180009cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cf5  lea     r8, [rsi+5Ch]; enum MilPixelFormat::Enum *
0x180009cf9  mov     rdx, rdi; struct IMILBitmapSource *
0x180009cfc  lea     rcx, [rsi-48h]; this
0x180009d00  call    ?GetPixelFormatExtended@CIcmColorTransform@@AEAAJPEAUIMILBitmapSource@@PEAW4Enum@MilPixelFormat@@@Z; CIcmColorTransform::GetPixelFormatExtended(IMILBitmapSource *,MilPixelFormat::Enum *)
0x180009d05  mov     edi, eax
0x180009d07  test    eax, eax
0x180009d09  js      loc_180009C1A
0x180009d0f  lea     rcx, [rsi-48h]; this
0x180009d13  lea     rdx, [rbp+arg_0]; int *
0x180009d17  call    ?SetupCompatibleTransform@CIcmColorTransform@@IEAAJPEAH@Z; CIcmColorTransform::SetupCompatibleTransform(int *)
0x180009d1c  mov     edi, eax
0x180009d1e  test    eax, eax
0x180009d20  js      loc_180009C1A
0x180009d26  cmp     dword ptr [rbp+arg_0], 1
0x180009d2a  jz      short loc_180009D4A
0x180009d2c  mov     rax, [rsi+38h]
0x180009d30  lea     r8, [rsi+48h]
0x180009d34  lea     rdx, IID_IMILBitmap
0x180009d3b  mov     rcx, [rax]
0x180009d3e  mov     rax, [rcx]
0x180009d41  mov     rcx, [rsi+38h]
0x180009d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d4a  call    ?EnsureLoaded@ICMModule@@SAHXZ; ICMModule::EnsureLoaded(void)
0x180009d4f  test    eax, eax
0x180009d51  jz      short loc_180009DB5
0x180009d53  xorps   xmm0, xmm0
0x180009d56  mov     [rbp+arg_0], 0
0x180009d5e  movups  [rbp+var_10], xmm0
0x180009d62  mov     qword ptr [rbp+var_10], r12
0x180009d66  xor     edi, edi
0x180009d68  mov     qword ptr [rbp+var_10+8], r15
0x180009d6c  call    ?EnsureLoaded@ICMModule@@SAHXZ; ICMModule::EnsureLoaded(void)
0x180009d71  test    eax, eax
0x180009d73  jz      short loc_180009D9E
0x180009d75  mov     rax, cs:?s_pfnCreateMultiProfileTransform@ICMModule@@0P6APEAXPEAPEAXKPEAKKKK@ZEA; void * (*ICMModule::s_pfnCreateMultiProfileTransform)(void * *,ulong,ulong *,ulong,ulong,ulong)
0x180009d7c  lea     edx, [rdi+2]
0x180009d7f  mov     r9d, edx
0x180009d82  mov     [rsp+50h+var_28], edi
0x180009d86  lea     r8, [rbp+arg_0]
0x180009d8a  mov     [rsp+50h+var_30], 20003h
0x180009d92  lea     rcx, [rbp+var_10]
0x180009d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d9b  mov     rdi, rax
0x180009d9e  mov     [rsi+50h], rdi
0x180009da2  test    rdi, rdi
0x180009da5  jnz     loc_180009C39
0x180009dab  mov     edi, 800707DBh
0x180009db0  jmp     loc_180009C1A
0x180009db5  mov     edi, 88982F50h
0x180009dba  jmp     loc_180009C1A
0x180009dbf  mov     rax, [rsi+38h]
0x180009dc3  mov     rcx, [rax]
0x180009dc6  mov     rax, [rcx+10h]
0x180009dca  mov     rcx, [rsi+38h]
0x180009dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dd3  jmp     loc_180009CE2
```
