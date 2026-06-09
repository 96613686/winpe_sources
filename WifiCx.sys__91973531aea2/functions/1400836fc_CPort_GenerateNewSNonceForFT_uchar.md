# CPort::GenerateNewSNonceForFT(uchar * *)

- ea: `0x1400836fc`
- end: `0x1400837e6`
- name: `?GenerateNewSNonceForFT@CPort@@QEAAHPEAPEAE@Z`
- size: `234`
- prototype: `int(CPort *__hidden this, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400a1f9c`

## callees

- `0x14000c778`
- `0x14001a630`
- `0x14002a9f8`
- `0x1400836fc`
- `0x1400dfd00`

## import_xrefs

- `cng!SystemPrng` at `0x140083737`
- `cng!SystemPrng` at `0x140083737`

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
  v5 = CPropertyCache::SetPropertyBuffer((CPort *)((char *)this + 480), 0x13u, 0x20u, v8);
  if ( v5 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        1,
        420,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        v5);
    }
    return v5;
  }
  else
  {
    v7 = 0;
    return CPropertyCache::GetPropertyBuffer((CPort *)((char *)this + 480), 0x13u, &v7, a2);
  }
}

```

## disassembly

```asm
0x1400836fc  mov     [rsp+arg_10], rbx
0x140083701  mov     [rsp+arg_18], rsi
0x140083706  push    rdi
0x140083707  sub     rsp, 60h
0x14008370b  mov     rax, cs:__security_cookie
0x140083712  xor     rax, rsp
0x140083715  mov     [rsp+68h+var_10], rax
0x14008371a  xorps   xmm0, xmm0
0x14008371d  mov     rsi, rdx
0x140083720  mov     rdi, rcx
0x140083723  mov     edx, 20h ; ' '
0x140083728  lea     rcx, [rsp+68h+var_30]
0x14008372d  movups  xmmword ptr [rsp+68h+var_30], xmm0
0x140083732  movups  [rsp+68h+var_20], xmm0
0x140083737  call    cs:__imp_SystemPrng
0x14008373e  nop     dword ptr [rax+rax+00h]
0x140083743  mov     edx, 13h; unsigned int
0x140083748  lea     r9, [rsp+68h+var_30]; unsigned __int8 *
0x14008374d  lea     rcx, [rdi+1E0h]; this
0x140083754  lea     r8d, [rdx+0Dh]; unsigned int
0x140083758  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEBE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar const *)
0x14008375d  mov     ebx, eax
0x14008375f  test    eax, eax
0x140083761  jz      short loc_1400837A5
0x140083763  lea     rax, WPP_RECORDER_INITIALIZED
0x14008376a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140083771  jz      short loc_1400837A1
0x140083773  mov     rcx, cs:WPP_GLOBAL_Control
0x14008377a  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140083781  mov     r9d, 1A4h
0x140083787  mov     [rsp+68h+var_40], ebx
0x14008378b  mov     r8d, 1
0x140083791  mov     [rsp+68h+var_48], rax
0x140083796  mov     dl, 2
0x140083798  mov     rcx, [rcx+40h]
0x14008379c  call    WPP_RECORDER_SF_d
0x1400837a1  mov     eax, ebx
0x1400837a3  jmp     short loc_1400837C6
0x1400837a5  mov     r9, rsi; unsigned __int8 **
0x1400837a8  mov     [rsp+68h+var_38], 0
0x1400837b0  lea     r8, [rsp+68h+var_38]; unsigned int *
0x1400837b5  mov     edx, 13h; unsigned int
0x1400837ba  lea     rcx, [rdi+1E0h]; this
0x1400837c1  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400837c6  mov     rcx, [rsp+68h+var_10]
0x1400837cb  xor     rcx, rsp; StackCookie
0x1400837ce  call    __security_check_cookie
0x1400837d3  lea     r11, [rsp+68h+var_8]
0x1400837d8  mov     rbx, [r11+20h]
0x1400837dc  mov     rsi, [r11+28h]
0x1400837e0  mov     rsp, r11
0x1400837e3  pop     rdi
0x1400837e4  retn
```
