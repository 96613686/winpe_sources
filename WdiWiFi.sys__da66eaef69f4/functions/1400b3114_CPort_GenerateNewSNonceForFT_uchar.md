# CPort::GenerateNewSNonceForFT(uchar * *)

- ea: `0x1400b3114`
- end: `0x1400b31fe`
- name: `?GenerateNewSNonceForFT@CPort@@QEAAHPEAPEAE@Z`
- size: `234`
- prototype: `int(CPort *__hidden this, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140073ecc`

## callees

- `0x140010390`
- `0x1400109f8`
- `0x140034ec4`
- `0x1400b3114`
- `0x1400da4f0`

## import_xrefs

- `cng!SystemPrng` at `0x1400b314f`
- `cng!SystemPrng` at `0x1400b314f`

## pseudocode

```c
__int64 __fastcall CPort::GenerateNewSNonceForFT(CPort *this, unsigned __int8 **a2)
{
  int v4; // edx
  unsigned int v5; // ebx
  unsigned int v7; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 v8[16]; // [rsp+38h] [rbp-30h] BYREF
  __int128 v9; // [rsp+48h] [rbp-20h]

  *(_OWORD *)v8 = 0;
  v9 = 0;
  SystemPrng(v8, 32);
  v5 = CPropertyCache::SetPropertyBuffer(&this->m_PortPropertyCache, 0x13u, 0x20u, v8);
  if ( v5 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        1,
        513,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        v5);
    }
    return v5;
  }
  else
  {
    v7 = 0;
    return CPropertyCache::GetPropertyBuffer(&this->m_PortPropertyCache, 0x13u, &v7, a2);
  }
}

```

## disassembly

```asm
0x1400b3114  mov     [rsp+arg_10], rbx
0x1400b3119  mov     [rsp+arg_18], rsi
0x1400b311e  push    rdi
0x1400b311f  sub     rsp, 60h
0x1400b3123  mov     rax, cs:__security_cookie
0x1400b312a  xor     rax, rsp
0x1400b312d  mov     [rsp+68h+var_10], rax
0x1400b3132  xorps   xmm0, xmm0
0x1400b3135  mov     rsi, rdx
0x1400b3138  mov     rdi, rcx
0x1400b313b  mov     edx, 20h ; ' '
0x1400b3140  lea     rcx, [rsp+68h+var_30]
0x1400b3145  movups  xmmword ptr [rsp+68h+var_30], xmm0
0x1400b314a  movups  [rsp+68h+var_20], xmm0
0x1400b314f  call    cs:__imp_SystemPrng
0x1400b3156  nop     dword ptr [rax+rax+00h]
0x1400b315b  mov     edx, 13h; unsigned int
0x1400b3160  lea     r9, [rsp+68h+var_30]; unsigned __int8 *
0x1400b3165  lea     rcx, [rdi+3A8h]; this
0x1400b316c  lea     r8d, [rdx+0Dh]; unsigned int
0x1400b3170  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEAE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar *)
0x1400b3175  mov     ebx, eax
0x1400b3177  test    eax, eax
0x1400b3179  jz      short loc_1400B31BD
0x1400b317b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b3182  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b3189  jz      short loc_1400B31B9
0x1400b318b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3192  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b3199  mov     r9d, 201h
0x1400b319f  mov     [rsp+68h+var_40], ebx
0x1400b31a3  mov     r8d, 1
0x1400b31a9  mov     [rsp+68h+var_48], rax
0x1400b31ae  mov     dl, 2
0x1400b31b0  mov     rcx, [rcx+40h]
0x1400b31b4  call    WPP_RECORDER_SF_D
0x1400b31b9  mov     eax, ebx
0x1400b31bb  jmp     short loc_1400B31DE
0x1400b31bd  mov     r9, rsi; unsigned __int8 **
0x1400b31c0  mov     [rsp+68h+var_38], 0
0x1400b31c8  lea     r8, [rsp+68h+var_38]; unsigned int *
0x1400b31cd  mov     edx, 13h; unsigned int
0x1400b31d2  lea     rcx, [rdi+3A8h]; this
0x1400b31d9  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400b31de  mov     rcx, [rsp+68h+var_10]
0x1400b31e3  xor     rcx, rsp; StackCookie
0x1400b31e6  call    __security_check_cookie
0x1400b31eb  lea     r11, [rsp+68h+var_8]
0x1400b31f0  mov     rbx, [r11+20h]
0x1400b31f4  mov     rsi, [r11+28h]
0x1400b31f8  mov     rsp, r11
0x1400b31fb  pop     rdi
0x1400b31fc  retn
```
