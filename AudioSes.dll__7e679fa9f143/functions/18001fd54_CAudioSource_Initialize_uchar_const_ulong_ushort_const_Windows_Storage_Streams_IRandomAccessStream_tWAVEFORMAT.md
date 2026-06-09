# CAudioSource::Initialize(uchar const *,ulong,ushort const *,Windows::Storage::Streams::IRandomAccessStream *,tWAVEFORMATEX const *)

- ea: `0x18001fd54`
- end: `0x1800200e8`
- name: `?Initialize@CAudioSource@@IEAAJPEBEKPEBGPEAUIRandomAccessStream@Streams@Storage@Windows@@PEBUtWAVEFORMATEX@@@Z`
- size: `916`
- prototype: `__int64 __fastcall(CAudioSource *__hidden this, const unsigned __int8 *, unsigned int, const unsigned __int16 *, struct Windows::Storage::Streams::IRandomAccessStream *, const struct tWAVEFORMATEX *)`
- caller_count: `6`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001fb00`
- `0x180020f38`
- `0x1800213ac`
- `0x1800c606c`
- `0x1800c637c`
- `0x1800c7610`

## callees

- `0x18000b9fc`
- `0x18001fd54`
- `0x1800200f0`
- `0x180020c44`
- `0x180088ce8`
- `0x18008ac99`
- `0x1800cbc08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fe54`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fe89`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ff35`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ff55`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ff60`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ffbc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ffc9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002004d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020057`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002007f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020091`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800200bb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800200c4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fe54`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fe89`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ff35`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ff55`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ff60`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ffbc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ffc9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002004d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020057`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002007f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020091`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800200bb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800200c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002003c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020075`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002003c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020075`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAudioSource::Initialize(
        CAudioSource *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        struct Windows::Storage::Streams::IRandomAccessStream *a5,
        const struct tWAVEFORMATEX *a6)
{
  unsigned __int8 *v7; // rdi
  char *v8; // rsi
  size_t v9; // r12
  unsigned int v10; // r15d
  unsigned int v11; // r12d
  int v12; // r14d
  int v13; // eax
  unsigned int v14; // eax
  size_t v15; // rbx
  size_t v16; // r8
  unsigned __int8 *v17; // rbx
  int v18; // r12d
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned __int8 *v22; // rcx
  unsigned __int16 v23; // ax
  int v24; // ebx
  char v25; // al
  unsigned int v27; // [rsp+40h] [rbp-40h] BYREF
  _BYTE Size[12]; // [rsp+44h] [rbp-3Ch] BYREF
  void *v29; // [rsp+50h] [rbp-30h] BYREF
  void *Block; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v31; // [rsp+60h] [rbp-20h]
  unsigned __int8 *v32; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int8 *v33; // [rsp+70h] [rbp-10h]
  const unsigned __int8 *v34; // [rsp+C8h] [rbp+48h]
  unsigned int v35; // [rsp+D0h] [rbp+50h]

  v35 = a3;
  v34 = a2;
  Block = 0;
  v27 = 0;
  v7 = 0;
  v33 = 0;
  v31 = 0;
  v8 = 0;
  v29 = 0;
  LODWORD(v9) = 0;
  v32 = 0;
  *(_QWORD *)Size = 0;
  v10 = -2147024882;
  if ( a6 )
  {
    v11 = a6->cbSize + 18;
    *(_DWORD *)Size = v11;
    v12 = 0;
  }
  else
  {
    v13 = CAudioSource::GuardedParseWaveRiffAndValidateFormatChunk(
            (CAudioSource *)Size,
            a2,
            a3,
            (const unsigned __int8 **)&v32,
            (unsigned int *)Size,
            (const unsigned __int8 **)&Block,
            &v27);
    v12 = v13;
    if ( v13 == -2147024882 || v13 == -2147024866 )
    {
      v10 = v13;
      goto LABEL_44;
    }
    v34 = (const unsigned __int8 *)Block;
    v35 = v27;
    if ( v13 < 0 )
    {
LABEL_32:
      if ( a4 || a5 )
      {
        *(_QWORD *)&Size[4] = 0;
        v24 = InitializeMFEncodedSourceStream(
                a4,
                a5,
                (struct tWAVEFORMATEX **)&Size[4],
                (unsigned int *)Size,
                (struct IDecodedAudioSourceStream **)this + 7);
        if ( v24 >= 0 )
        {
          v9 = *(unsigned int *)Size;
          v25 = ATL::CHeapPtrBase<unsigned char,ATL::CCRTAllocator>::AllocateBytes(&v29, *(unsigned int *)Size);
          v8 = (char *)v29;
          if ( v25 )
          {
            memcpy_0(v29, *(const void **)&Size[4], v9);
            CoTaskMemFree(*(LPVOID *)&Size[4]);
            goto LABEL_42;
          }
          v24 = -2147024882;
        }
        CoTaskMemFree(*(LPVOID *)&Size[4]);
        *(_QWORD *)&Size[4] = 0;
        goto LABEL_40;
      }
      if ( v12 < 0 )
      {
        v24 = -2147024809;
LABEL_40:
        free(v8);
        free(v7);
        return (unsigned int)v24;
      }
LABEL_42:
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = v8;
      *((_DWORD *)this + 4) = v9;
      free(*((void **)this + 5));
      *((_QWORD *)this + 5) = v7;
      *((_DWORD *)this + 12) = v31;
      *((_QWORD *)this + 3) = v34;
      *((_DWORD *)this + 8) = v35;
      v10 = 0;
      goto LABEL_44;
    }
    a6 = (const struct tWAVEFORMATEX *)v32;
    v11 = *(_DWORD *)Size;
  }
  Block = 0;
  v14 = 18;
  if ( v11 > 0x12 )
    v14 = v11;
  v27 = v14;
  v15 = v14;
  if ( !(unsigned __int8)ATL::CHeapPtrBase<unsigned char,ATL::CCRTAllocator>::AllocateBytes(&Block, v14) )
  {
    free(Block);
LABEL_44:
    free(0);
    v22 = 0;
    goto LABEL_45;
  }
  v16 = v15;
  v17 = (unsigned __int8 *)Block;
  memset_0(Block, 0, v16);
  v18 = GuardedCopyMemory(v17, (const unsigned __int8 *)a6, v11);
  if ( v18 < 0 )
  {
    free(v17);
    v10 = v18;
    goto LABEL_44;
  }
  if ( ((*(_WORD *)v17 - 1) & 0xFFFD) == 0 )
    goto LABEL_30;
  if ( *(_WORD *)v17 == 0xFFFE )
  {
    v19 = *((_QWORD *)v17 + 3) - *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1;
    if ( !v19 )
      v19 = *((_QWORD *)v17 + 4) - *(_QWORD *)GUID_00000001_0000_0010_8000_00aa00389b71.Data4;
    if ( !v19 )
      goto LABEL_30;
    v20 = *((_QWORD *)v17 + 3) - *(_QWORD *)&GUID_00000003_0000_0010_8000_00aa00389b71.Data1;
    if ( !v20 )
      v20 = *((_QWORD *)v17 + 4) - *(_QWORD *)GUID_00000003_0000_0010_8000_00aa00389b71.Data4;
    if ( !v20 )
    {
LABEL_30:
      LODWORD(v9) = v27;
      v8 = (char *)v17;
      v17 = 0;
      free(0);
      v29 = v8;
LABEL_31:
      free(v17);
      if ( v12 >= 0 )
        goto LABEL_42;
      goto LABEL_32;
    }
  }
  if ( *(_WORD *)v17 != 85 )
  {
    if ( *(_WORD *)v17 != 0xFFFE )
      goto LABEL_26;
    v21 = *((_QWORD *)v17 + 3) - *(_QWORD *)&GUID_00000055_0000_0010_8000_00aa00389b71.Data1;
    if ( !v21 )
      v21 = *((_QWORD *)v17 + 4) - *(_QWORD *)GUID_00000055_0000_0010_8000_00aa00389b71.Data4;
    if ( v21 )
    {
LABEL_26:
      v12 = -2147467259;
      LODWORD(v9) = *(_DWORD *)&Size[4];
      goto LABEL_31;
    }
  }
  v7 = v17;
  v17 = 0;
  free(0);
  v33 = v7;
  LODWORD(v9) = 18;
  if ( (unsigned __int8)ATL::CHeapPtrBase<unsigned char,ATL::CCRTAllocator>::AllocateBytes(&v29, 18) )
  {
    v31 = v27;
    v8 = (char *)v29;
    *(_WORD *)v29 = 1;
    *((_WORD *)v8 + 1) = *((_WORD *)v7 + 1);
    *((_DWORD *)v8 + 1) = *((_DWORD *)v7 + 1);
    *(_DWORD *)(v8 + 14) = 16;
    v23 = 2 << (*((unsigned __int16 *)v8 + 1) >> 1);
    *((_WORD *)v8 + 6) = v23;
    *((_DWORD *)v8 + 2) = *((_DWORD *)v8 + 1) * v23;
    goto LABEL_31;
  }
  free(0);
  free(v29);
  v22 = v7;
LABEL_45:
  free(v22);
  return v10;
}

```

## disassembly

```asm
0x18001fd54  mov     rax, rsp
0x18001fd57  mov     [rax+8], rbx
0x18001fd5b  mov     [rax+20h], r9
0x18001fd5f  mov     [rax+18h], r8d
0x18001fd63  mov     [rax+10h], rdx
0x18001fd67  push    rbp
0x18001fd68  push    rsi
0x18001fd69  push    rdi
0x18001fd6a  push    r12
0x18001fd6c  push    r13
0x18001fd6e  push    r14
0x18001fd70  push    r15
0x18001fd72  mov     rbp, rsp
0x18001fd75  sub     rsp, 80h
0x18001fd7c  mov     r13, rcx
0x18001fd7f  xor     r9d, r9d
0x18001fd82  mov     [rbp+Block], r9
0x18001fd86  mov     [rbp+var_40], r9d
0x18001fd8a  mov     edi, r9d
0x18001fd8d  mov     [rbp+var_10], r9
0x18001fd91  mov     [rbp+var_20], r9d
0x18001fd95  mov     esi, r9d
0x18001fd98  mov     [rbp+var_30], r9
0x18001fd9c  mov     r12d, r9d
0x18001fd9f  mov     dword ptr [rbp+Size+4], r9d
0x18001fda3  mov     [rbp+var_18], r9
0x18001fda7  mov     dword ptr [rbp+Size], r9d
0x18001fdab  mov     r15d, 8007000Eh
0x18001fdb1  mov     rbx, [rbp+arg_28]
0x18001fdb5  test    rbx, rbx
0x18001fdb8  jz      short loc_18001FDCC
0x18001fdba  movzx   r12d, word ptr [rbx+10h]
0x18001fdbf  add     r12d, 12h
0x18001fdc3  mov     dword ptr [rbp+Size], r12d
0x18001fdc7  mov     r14d, r9d
0x18001fdca  jmp     short loc_18001FE2C
0x18001fdcc  lea     rcx, [rbp+var_40]
0x18001fdd0  mov     [rsp+80h+var_50], rcx; unsigned int *
0x18001fdd5  lea     rcx, [rbp+Block]
0x18001fdd9  mov     [rsp+80h+var_58], rcx; unsigned __int8 **
0x18001fdde  lea     rcx, [rbp+Size]; this
0x18001fde2  mov     [rsp+80h+var_60], rcx; unsigned int *
0x18001fde7  lea     r9, [rbp+var_18]; unsigned __int8 **
0x18001fdeb  call    ?GuardedParseWaveRiffAndValidateFormatChunk@CAudioSource@@AEAAJPEBEKPEAPEBEPEAK12@Z; CAudioSource::GuardedParseWaveRiffAndValidateFormatChunk(uchar const *,ulong,uchar const * *,ulong *,uchar const * *,ulong *)
0x18001fdf0  mov     r14d, eax
0x18001fdf3  cmp     eax, r15d
0x18001fdf6  jz      loc_1800200B6
0x18001fdfc  cmp     eax, 8007001Eh
0x18001fe01  jz      loc_1800200B6
0x18001fe07  xor     r9d, r9d
0x18001fe0a  test    eax, eax
0x18001fe0c  mov     rax, [rbp+Block]
0x18001fe10  mov     [rbp+arg_8], rax
0x18001fe14  mov     eax, [rbp+var_40]
0x18001fe17  mov     [rbp+arg_10], eax
0x18001fe1a  js      loc_18001FFDB
0x18001fe20  mov     rax, [rbp+var_18]
0x18001fe24  mov     [rbp+arg_28], rax
0x18001fe28  mov     r12d, dword ptr [rbp+Size]
0x18001fe2c  mov     [rbp+Block], r9
0x18001fe30  mov     eax, 12h
0x18001fe35  cmp     r12d, eax
0x18001fe38  cmova   eax, r12d
0x18001fe3c  mov     [rbp+var_40], eax
0x18001fe3f  mov     ebx, eax
0x18001fe41  mov     edx, eax
0x18001fe43  lea     rcx, [rbp+Block]
0x18001fe47  call    ?AllocateBytes@?$CHeapPtrBase@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<uchar,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x18001fe4c  test    al, al
0x18001fe4e  jnz     short loc_18001FE5F
0x18001fe50  mov     rcx, [rbp+Block]; Block
0x18001fe54  call    cs:__imp_free
0x18001fe5a  jmp     loc_1800200B9
0x18001fe5f  mov     r8, rbx; Size
0x18001fe62  xor     edx, edx; Val
0x18001fe64  mov     rbx, [rbp+Block]
0x18001fe68  mov     rcx, rbx; void *
0x18001fe6b  call    memset_0
0x18001fe70  mov     r8d, r12d; unsigned int
0x18001fe73  mov     rdx, [rbp+arg_28]; unsigned __int8 *
0x18001fe77  mov     rcx, rbx; unsigned __int8 *
0x18001fe7a  call    ?GuardedCopyMemory@@YAJPEAEPEBEK@Z; GuardedCopyMemory(uchar *,uchar const *,ulong)
0x18001fe7f  mov     r12d, eax
0x18001fe82  test    eax, eax
0x18001fe84  jns     short loc_18001FE97
0x18001fe86  mov     rcx, rbx; Block
0x18001fe89  call    cs:__imp_free
0x18001fe8f  mov     r15d, r12d
0x18001fe92  jmp     loc_1800200B9
0x18001fe97  movzx   eax, word ptr [rbx]
0x18001fe9a  dec     ax
0x18001fe9d  mov     ecx, 0FFFDh
0x18001fea2  test    cx, ax
0x18001fea5  jz      loc_18001FFB1
0x18001feab  mov     ecx, 0FFFEh
0x18001feb0  cmp     [rbx], cx
0x18001feb3  jnz     short loc_18001FEF7
0x18001feb5  mov     rax, [rbx+18h]
0x18001feb9  sub     rax, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data1
0x18001fec0  jnz     short loc_18001FECD
0x18001fec2  mov     rax, [rbx+20h]
0x18001fec6  sub     rax, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data4
0x18001fecd  test    rax, rax
0x18001fed0  jz      loc_18001FFB1
0x18001fed6  mov     rax, [rbx+18h]
0x18001feda  sub     rax, qword ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data1
0x18001fee1  jnz     short loc_18001FEEE
0x18001fee3  mov     rax, [rbx+20h]
0x18001fee7  sub     rax, qword ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data4
0x18001feee  test    rax, rax
0x18001fef1  jz      loc_18001FFB1
0x18001fef7  cmp     word ptr [rbx], 55h ; 'U'
0x18001fefb  jz      short loc_18001FF2E
0x18001fefd  cmp     [rbx], cx
0x18001ff00  jnz     short loc_18001FF1F
0x18001ff02  mov     rax, [rbx+18h]
0x18001ff06  sub     rax, qword ptr cs:_GUID_00000055_0000_0010_8000_00aa00389b71.Data1
0x18001ff0d  jnz     short loc_18001FF1A
0x18001ff0f  mov     rax, [rbx+20h]
0x18001ff13  sub     rax, qword ptr cs:_GUID_00000055_0000_0010_8000_00aa00389b71.Data4
0x18001ff1a  test    rax, rax
0x18001ff1d  jz      short loc_18001FF2E
0x18001ff1f  mov     r14d, 80004005h
0x18001ff25  mov     r12d, dword ptr [rbp+Size+4]
0x18001ff29  jmp     loc_18001FFC6
0x18001ff2e  mov     rdi, rbx
0x18001ff31  xor     ebx, ebx
0x18001ff33  xor     ecx, ecx; Block
0x18001ff35  call    cs:__imp_free
0x18001ff3b  mov     [rbp+var_10], rdi
0x18001ff3f  lea     r12d, [rbx+12h]
0x18001ff43  mov     edx, r12d
0x18001ff46  lea     rcx, [rbp+var_30]
0x18001ff4a  call    ?AllocateBytes@?$CHeapPtrBase@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<uchar,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x18001ff4f  test    al, al
0x18001ff51  jnz     short loc_18001FF6F
0x18001ff53  xor     ecx, ecx; Block
0x18001ff55  call    cs:__imp_free
0x18001ff5b  nop
0x18001ff5c  mov     rcx, [rbp+var_30]; Block
0x18001ff60  call    cs:__imp_free
0x18001ff66  nop
0x18001ff67  mov     rcx, rdi
0x18001ff6a  jmp     loc_1800200C4
0x18001ff6f  mov     eax, [rbp+var_40]
0x18001ff72  mov     [rbp+var_20], eax
0x18001ff75  mov     rsi, [rbp+var_30]
0x18001ff79  mov     word ptr [rsi], 1
0x18001ff7e  movzx   eax, word ptr [rdi+2]
0x18001ff82  mov     [rsi+2], ax
0x18001ff86  mov     eax, [rdi+4]
0x18001ff89  mov     [rsi+4], eax
0x18001ff8c  mov     dword ptr [rsi+0Eh], 10h
0x18001ff93  movzx   ecx, word ptr [rsi+2]
0x18001ff97  shr     ecx, 1
0x18001ff99  mov     eax, 2
0x18001ff9e  shl     ax, cl
0x18001ffa1  movzx   ecx, ax
0x18001ffa4  mov     [rsi+0Ch], cx
0x18001ffa8  imul    ecx, [rsi+4]
0x18001ffac  mov     [rsi+8], ecx
0x18001ffaf  jmp     short loc_18001FFC6
0x18001ffb1  mov     r12d, [rbp+var_40]
0x18001ffb5  mov     rsi, rbx
0x18001ffb8  xor     ebx, ebx
0x18001ffba  xor     ecx, ecx; Block
0x18001ffbc  call    cs:__imp_free
0x18001ffc2  mov     [rbp+var_30], rsi
0x18001ffc6  mov     rcx, rbx; Block
0x18001ffc9  call    cs:__imp_free
0x18001ffcf  xor     r9d, r9d
0x18001ffd2  test    r14d, r14d
0x18001ffd5  jns     loc_18002007B
0x18001ffdb  mov     rdx, [rbp+arg_20]; struct Windows::Storage::Streams::IRandomAccessStream *
0x18001ffdf  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x18001ffe3  test    rcx, rcx
0x18001ffe6  jnz     short loc_18001FFFD
0x18001ffe8  test    rdx, rdx
0x18001ffeb  jnz     short loc_18001FFFD
0x18001ffed  test    r14d, r14d
0x18001fff0  jns     loc_18002007B
0x18001fff6  mov     ebx, 80070057h
0x18001fffb  jmp     short loc_18002004A
0x18001fffd  mov     qword ptr [rbp+Size+4], r9
0x180020001  lea     rax, [r13+38h]
0x180020005  mov     [rsp+80h+var_60], rax; struct IDecodedAudioSourceStream **
0x18002000a  lea     r9, [rbp+Size]; unsigned int *
0x18002000e  lea     r8, [rbp+Size+4]; struct tWAVEFORMATEX **
0x180020012  call    ?InitializeMFEncodedSourceStream@@YAJPEBGPEAUIRandomAccessStream@Streams@Storage@Windows@@PEAPEAUtWAVEFORMATEX@@PEAKPEAPEAUIDecodedAudioSourceStream@@@Z; InitializeMFEncodedSourceStream(ushort const *,Windows::Storage::Streams::IRandomAccessStream *,tWAVEFORMATEX * *,ulong *,IDecodedAudioSourceStream * *)
0x180020017  mov     ebx, eax
0x180020019  test    eax, eax
0x18002001b  js      short loc_180020038
0x18002001d  mov     r12d, dword ptr [rbp+Size]
0x180020021  mov     edx, r12d
0x180020024  lea     rcx, [rbp+var_30]
0x180020028  call    ?AllocateBytes@?$CHeapPtrBase@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<uchar,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x18002002d  mov     rsi, [rbp+var_30]
0x180020031  test    al, al
0x180020033  jnz     short loc_180020061
0x180020035  mov     ebx, r15d
0x180020038  mov     rcx, qword ptr [rbp+Size+4]; pv
0x18002003c  call    cs:__imp_CoTaskMemFree
0x180020042  mov     qword ptr [rbp+Size+4], 0
0x18002004a  mov     rcx, rsi; Block
0x18002004d  call    cs:__imp_free
0x180020053  nop
0x180020054  mov     rcx, rdi; Block
0x180020057  call    cs:__imp_free
0x18002005d  mov     eax, ebx
0x18002005f  jmp     short loc_1800200CD
0x180020061  mov     r8, r12; Size
0x180020064  mov     rdx, qword ptr [rbp+Size+4]; Src
0x180020068  mov     rcx, rsi; void *
0x18002006b  call    memcpy_0
0x180020070  nop
0x180020071  mov     rcx, qword ptr [rbp+Size+4]; pv
0x180020075  call    cs:__imp_CoTaskMemFree
0x18002007b  mov     rcx, [r13+8]; Block
0x18002007f  call    cs:__imp_free
0x180020085  mov     [r13+8], rsi
0x180020089  mov     [r13+10h], r12d
0x18002008d  mov     rcx, [r13+28h]; Block
0x180020091  call    cs:__imp_free
0x180020097  mov     [r13+28h], rdi
0x18002009b  mov     eax, [rbp+var_20]
0x18002009e  mov     [r13+30h], eax
0x1800200a2  mov     rax, [rbp+arg_8]
0x1800200a6  mov     [r13+18h], rax
0x1800200aa  mov     eax, [rbp+arg_10]
0x1800200ad  mov     [r13+20h], eax
0x1800200b1  xor     r15d, r15d
0x1800200b4  jmp     short loc_1800200B9
0x1800200b6  mov     r15d, eax
0x1800200b9  xor     ecx, ecx; Block
0x1800200bb  call    cs:__imp_free
0x1800200c1  nop
0x1800200c2  xor     ecx, ecx; Block
0x1800200c4  call    cs:__imp_free
0x1800200ca  mov     eax, r15d
0x1800200cd  mov     rbx, [rsp+80h+arg_0]
0x1800200d5  add     rsp, 80h
0x1800200dc  pop     r15
0x1800200de  pop     r14
0x1800200e0  pop     r13
0x1800200e2  pop     r12
0x1800200e4  pop     rdi
0x1800200e5  pop     rsi
0x1800200e6  pop     rbp
0x1800200e7  retn
```
