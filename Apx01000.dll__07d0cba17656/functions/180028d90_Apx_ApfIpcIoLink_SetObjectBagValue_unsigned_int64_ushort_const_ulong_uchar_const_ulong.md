# Apx::ApfIpcIoLink::SetObjectBagValue(unsigned __int64,ushort const *,ulong,uchar const *,ulong)

- ea: `0x180028d90`
- end: `0x180029035`
- name: `?SetObjectBagValue@ApfIpcIoLink@Apx@@UEAAJ_KPEBGKPEBEK@Z`
- size: `677`
- prototype: `__int64 __fastcall(unsigned __int64 this, __int64, const unsigned __int16 *, int, const unsigned __int8 *Src, size_t Size)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x180002100`
- `0x18000213c`
- `0x1800027c8`
- `0x18000ba84`
- `0x180011e6c`
- `0x180028d90`
- `0x1800294b8`
- `0x18002956c`
- `0x180029880`

## pseudocode

```c
__int64 __fastcall Apx::ApfIpcIoLink::SetObjectBagValue(
        unsigned __int64 this,
        __int64 a2,
        const unsigned __int16 *a3,
        int a4,
        const unsigned __int8 *Src,
        size_t Size)
{
  int v6; // ebx
  DWORD nInBufferSize; // r14d
  char *v10; // rax
  __int64 v11; // r8
  char *v12; // rsi
  unsigned int v13; // ebx
  _QWORD *v14; // r12
  __int64 v15; // rax
  _WORD *v16; // r8
  const unsigned __int16 *v17; // rcx
  __int64 v18; // rdx
  _WORD *v19; // rcx

  v6 = 0;
  nInBufferSize = 552;
  if ( !(_DWORD)Size || !Src )
  {
LABEL_5:
    v10 = (char *)operator new[](nInBufferSize, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, nInBufferSize);
      v14 = (_QWORD *)(this + 64);
      *(_QWORD *)v12 = *(_QWORD *)(this + 64);
      *((_QWORD *)v12 + 1) = a2;
      *((_DWORD *)v12 + 5) = a4;
      *((_DWORD *)v12 + 4) = v6;
      *((_DWORD *)v12 + 6) = Size;
      if ( v6 )
        memcpy_0(v12 + 548, Src, (unsigned int)Size);
      v15 = 2147483646;
      v16 = v12 + 28;
      v17 = a3;
      v18 = 260;
      do
      {
        if ( !v15 )
          break;
        if ( !*v17 )
          break;
        *v16++ = *v17++;
        --v15;
        --v18;
      }
      while ( v18 );
      v19 = v16 - 1;
      v13 = v18 == 0 ? 0x8007007A : 0;
      if ( v18 )
        v19 = v16;
      *v19 = 0;
      if ( v18 )
      {
        v13 = Apx::ApfHelper::SyncIoctl(*(void **)(this + 112), 0x1388u, 0x1DC080u, v12, nInBufferSize, 0, 0, 0, 0);
        if ( (v13 & 0x80000000) == 0 )
        {
          v13 = 0;
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && *((char *)WPP_GLOBAL_Control + 28) < 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_qqd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            40,
            &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids,
            ~this,
            *v14,
            v13);
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && *((char *)WPP_GLOBAL_Control + 28) < 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_qiSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 0, (_DWORD)v16, ~(_DWORD)this, *v14, (__int64)a3, 122);
      }
      operator delete(v12, (const struct std::nothrow_t *)v18);
    }
    else
    {
      v13 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_qidd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          v11,
          ~this,
          *(_QWORD *)(this + 64),
          nInBufferSize,
          -2147024882);
      }
    }
    return v13;
  }
  if ( (unsigned int)(Size + 552) >= 0x228 )
  {
    nInBufferSize = Size + 552;
    v6 = 1;
    goto LABEL_5;
  }
  v13 = -2147024362;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qidd(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, a3, ~this, *(_QWORD *)(this + 64), Size, -2147024362);
  }
  return v13;
}

```

## disassembly

```asm
0x180028d90  mov     rax, rsp
0x180028d93  mov     [rax+8], rbx
0x180028d97  mov     [rax+18h], rbp
0x180028d9b  mov     [rax+20h], r9d
0x180028d9f  mov     [rax+10h], rdx
0x180028da3  push    rsi
0x180028da4  push    rdi
0x180028da5  push    r12
0x180028da7  push    r13
0x180028da9  push    r14
0x180028dab  sub     rsp, 50h
0x180028daf  mov     ebp, dword ptr [rsp+78h+Size]
0x180028db6  xor     ebx, ebx
0x180028db8  mov     r13, r8
0x180028dbb  mov     rdi, rcx
0x180028dbe  mov     r14d, 228h
0x180028dc4  test    ebp, ebp
0x180028dc6  jz      short loc_180028DE5
0x180028dc8  cmp     [rsp+78h+Src], rbx
0x180028dd0  jz      short loc_180028DE5
0x180028dd2  lea     eax, [rbp+228h]
0x180028dd8  cmp     eax, r14d
0x180028ddb  jb      short loc_180028E41
0x180028ddd  mov     r14d, eax
0x180028de0  mov     ebx, 1
0x180028de5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028dec  mov     ecx, r14d; unsigned __int64
0x180028def  mov     r12d, r14d
0x180028df2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180028df7  mov     rsi, rax
0x180028dfa  test    rax, rax
0x180028dfd  jnz     loc_180028E9B
0x180028e03  mov     ebx, 8007000Eh
0x180028e08  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e0f  lea     rax, WPP_GLOBAL_Control
0x180028e16  cmp     rcx, rax
0x180028e19  jz      loc_18002901A
0x180028e1f  test    byte ptr [rcx+1Ch], 80h
0x180028e23  jz      loc_18002901A
0x180028e29  cmp     byte ptr [rcx+19h], 2
0x180028e2d  jb      loc_18002901A
0x180028e33  mov     [rsp+78h+var_48], ebx
0x180028e37  lea     edx, [rsi+26h]
0x180028e3a  mov     dword ptr [rsp+78h+var_50], r14d
0x180028e3f  jmp     short loc_180028E7E
0x180028e41  mov     ebx, 80070216h
0x180028e46  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e4d  lea     rax, WPP_GLOBAL_Control
0x180028e54  cmp     rcx, rax
0x180028e57  jz      loc_18002901A
0x180028e5d  test    byte ptr [rcx+1Ch], 80h
0x180028e61  jz      loc_18002901A
0x180028e67  cmp     byte ptr [rcx+19h], 2
0x180028e6b  jb      loc_18002901A
0x180028e71  mov     [rsp+78h+var_48], ebx
0x180028e75  mov     edx, 25h ; '%'
0x180028e7a  mov     dword ptr [rsp+78h+var_50], ebp
0x180028e7e  mov     rax, [rdi+40h]
0x180028e82  mov     r9, rdi
0x180028e85  mov     rcx, [rcx+10h]
0x180028e89  not     r9
0x180028e8c  mov     qword ptr [rsp+78h+nInBufferSize], rax
0x180028e91  call    WPP_SF_qidd
0x180028e96  jmp     loc_18002901A
0x180028e9b  mov     r8, r12; Size
0x180028e9e  xor     edx, edx; Val
0x180028ea0  mov     rcx, rsi; void *
0x180028ea3  call    memset_0
0x180028ea8  lea     r12, [rdi+40h]
0x180028eac  mov     rax, [r12]
0x180028eb0  mov     [rsi], rax
0x180028eb3  mov     rax, [rsp+78h+arg_8]
0x180028ebb  mov     [rsi+8], rax
0x180028ebf  mov     eax, [rsp+78h+arg_18]
0x180028ec6  mov     [rsi+14h], eax
0x180028ec9  mov     [rsi+10h], ebx
0x180028ecc  mov     [rsi+18h], ebp
0x180028ecf  test    ebx, ebx
0x180028ed1  jz      short loc_180028EEA
0x180028ed3  mov     rdx, [rsp+78h+Src]; Src
0x180028edb  lea     rcx, [rsi+224h]; void *
0x180028ee2  mov     r8, rbp; Size
0x180028ee5  call    memcpy_0
0x180028eea  mov     eax, 7FFFFFFEh
0x180028eef  lea     r8, [rsi+1Ch]
0x180028ef3  mov     rcx, r13
0x180028ef6  mov     edx, 104h
0x180028efb  xor     ebp, ebp
0x180028efd  test    rax, rax
0x180028f00  jz      short loc_180028F21
0x180028f02  movzx   r9d, word ptr [rcx]
0x180028f06  test    r9w, r9w
0x180028f0a  jz      short loc_180028F21
0x180028f0c  mov     [r8], r9w
0x180028f10  add     rcx, 2
0x180028f14  add     r8, 2
0x180028f18  dec     rax
0x180028f1b  sub     rdx, 1
0x180028f1f  jnz     short loc_180028EFD
0x180028f21  mov     rax, rdx
0x180028f24  lea     rcx, [r8-2]
0x180028f28  neg     rax
0x180028f2b  sbb     ebx, ebx
0x180028f2d  not     ebx
0x180028f2f  and     ebx, 8007007Ah
0x180028f35  test    rdx, rdx
0x180028f38  cmovnz  rcx, r8
0x180028f3c  mov     [rcx], bp
0x180028f3f  jnz     short loc_180028F92
0x180028f41  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f48  lea     rax, WPP_GLOBAL_Control
0x180028f4f  cmp     rcx, rax
0x180028f52  jz      loc_180029012
0x180028f58  test    byte ptr [rcx+1Ch], 80h
0x180028f5c  jz      loc_180029012
0x180028f62  cmp     byte ptr [rcx+19h], 2
0x180028f66  jb      loc_180029012
0x180028f6c  mov     rax, [r12]
0x180028f70  not     rdi
0x180028f73  mov     rcx, [rcx+10h]
0x180028f77  mov     r9, rdi
0x180028f7a  mov     [rsp+78h+var_48], ebx
0x180028f7e  mov     [rsp+78h+var_50], r13
0x180028f83  mov     qword ptr [rsp+78h+nInBufferSize], rax
0x180028f88  call    WPP_SF_qiSd
0x180028f8d  jmp     loc_180029012
0x180028f92  mov     rcx, [rdi+70h]; void *
0x180028f96  mov     r9, rsi; void *
0x180028f99  mov     [rsp+78h+var_38], rbp; void *
0x180028f9e  mov     edx, 1388h; unsigned int
0x180028fa3  mov     [rsp+78h+lpNumberOfBytesTransferred], rbp; lpNumberOfBytesTransferred
0x180028fa8  mov     r8d, 1DC080h; unsigned int
0x180028fae  mov     [rsp+78h+var_48], ebp; DWORD
0x180028fb2  mov     [rsp+78h+var_50], rbp; void *
0x180028fb7  mov     [rsp+78h+nInBufferSize], r14d; nInBufferSize
0x180028fbc  call    ?SyncIoctl@ApfHelper@Apx@@SAJPEAXKK0K0KPEAK0@Z; Apx::ApfHelper::SyncIoctl(void *,ulong,ulong,void *,ulong,void *,ulong,ulong *,void *)
0x180028fc1  mov     ebx, eax
0x180028fc3  test    eax, eax
0x180028fc5  jns     short loc_180029010
0x180028fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180028fce  lea     rax, WPP_GLOBAL_Control
0x180028fd5  cmp     rcx, rax
0x180028fd8  jz      short loc_180029012
0x180028fda  test    byte ptr [rcx+1Ch], 80h
0x180028fde  jz      short loc_180029012
0x180028fe0  cmp     byte ptr [rcx+19h], 3
0x180028fe4  jb      short loc_180029012
0x180028fe6  mov     rax, [r12]
0x180028fea  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180028ff1  mov     rcx, [rcx+10h]
0x180028ff5  not     rdi
0x180028ff8  mov     r9, rdi
0x180028ffb  mov     dword ptr [rsp+78h+var_50], ebx
0x180028fff  mov     edx, 28h ; '('
0x180029004  mov     qword ptr [rsp+78h+nInBufferSize], rax
0x180029009  call    WPP_SF_qqd
0x18002900e  jmp     short loc_180029012
0x180029010  mov     ebx, ebp
0x180029012  mov     rcx, rsi; void *
0x180029015  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002901a  lea     r11, [rsp+78h+var_28]
0x18002901f  mov     eax, ebx
0x180029021  mov     rbx, [r11+30h]
0x180029025  mov     rbp, [r11+40h]
0x180029029  mov     rsp, r11
0x18002902c  pop     r14
0x18002902e  pop     r13
0x180029030  pop     r12
0x180029032  pop     rdi
0x180029033  pop     rsi
0x180029034  retn
```
