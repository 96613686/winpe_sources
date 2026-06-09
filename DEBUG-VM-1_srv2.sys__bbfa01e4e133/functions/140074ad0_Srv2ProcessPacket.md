# Srv2ProcessPacket

- ea: `0x140074ad0`
- end: `0x140074c3d`
- name: `Srv2ProcessPacket`
- size: `365`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14005d3d0`
- `0x140074970`

## callees

- `0x140005070`
- `0x140008200`
- `0x140019ab8`
- `0x1400222ec`
- `0x140038490`
- `0x140074ad0`
- `0x14008d678`

## import_xrefs

- `ntoskrnl!IoClearActivityIdThread` at `0x140074bfd`
- `ntoskrnl!IoClearActivityIdThread` at `0x140074bfd`
- `ntoskrnl!IoSetActivityIdThread` at `0x140074be3`
- `ntoskrnl!IoSetActivityIdThread` at `0x140074be3`

## pseudocode

```c
__int64 __fastcall Srv2ProcessPacket(__int64 a1)
{
  __int64 v1; // rsi
  char v2; // di
  __int64 i; // rax
  __int64 result; // rax
  __int128 v6; // [rsp+30h] [rbp-28h] BYREF

  v1 = 0;
  v2 = 0;
  v6 = 0;
  if ( (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
  {
    SRV2_PERF_ISSUE_RECEIVE_CORRELATION(a1);
    if ( (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
    {
      v6 = *(_OWORD *)(a1 + 584);
      v1 = IoSetActivityIdThread(&v6);
      v2 = 1;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_42ed7384cb6a3283aec034377101fac6_Traceguids, a1);
  }
  if ( !*(_QWORD *)(a1 + 512) )
  {
    for ( i = Srv2ProviderList; Srv2ProviderList; i = *(_QWORD *)(i + 32) )
    {
      if ( (*(_DWORD *)(a1 + 392) & *(_DWORD *)(i + 44)) != 0 )
        break;
    }
    *(_QWORD *)(a1 + 512) = i;
  }
  if ( !*(_BYTE *)(*(_QWORD *)(a1 + 96) + 508LL) )
    Srv2InitializeConnectionPassive();
  SRV2_PERF_ENTER_EX(a1 + 584, 0, 121, "Srv2ProcessPacket", 1);
  result = Srv2CallProviders(a1, 0, 0);
  if ( v2 )
    return IoClearActivityIdThread(v1);
  return result;
}

```

## disassembly

```asm
0x140074ad0  mov     [rsp+arg_8], rbx
0x140074ad5  mov     [rsp+arg_10], rsi
0x140074ada  push    rdi
0x140074adb  sub     rsp, 50h
0x140074adf  mov     rax, cs:__security_cookie
0x140074ae6  xor     rax, rsp
0x140074ae9  mov     [rsp+58h+var_18], rax
0x140074aee  xor     esi, esi
0x140074af0  xor     dil, dil
0x140074af3  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x140074afa  xorps   xmm0, xmm0
0x140074afd  mov     rbx, rcx
0x140074b00  movups  [rsp+58h+var_28], xmm0
0x140074b05  jnz     loc_140074BC0
0x140074b0b  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140074b12  lea     rax, WPP_GLOBAL_Control
0x140074b19  cmp     r10, rax
0x140074b1c  jz      short loc_140074B2B
0x140074b1e  mov     ecx, [r10+2Ch]
0x140074b22  test    cl, 40h
0x140074b25  jnz     loc_140074C0B
0x140074b2b  cmp     qword ptr [rbx+200h], 0
0x140074b33  jnz     short loc_140074B5F
0x140074b35  mov     r8, cs:Srv2ProviderList
0x140074b3c  mov     rax, r8
0x140074b3f  test    r8, r8
0x140074b42  jz      short loc_140074B58
0x140074b44  mov     edx, [rbx+188h]
0x140074b4a  test    [rax+2Ch], edx
0x140074b4d  jnz     short loc_140074B58
0x140074b4f  mov     rax, [rax+20h]
0x140074b53  test    r8, r8
0x140074b56  jnz     short loc_140074B4A
0x140074b58  mov     [rbx+200h], rax
0x140074b5f  mov     rcx, [rbx+60h]
0x140074b63  cmp     byte ptr [rcx+1FCh], 0
0x140074b6a  jz      loc_140074C33
0x140074b70  lea     rcx, [rbx+248h]
0x140074b77  mov     [rsp+58h+var_38], 1
0x140074b7c  lea     r9, aSrv2processpac; "Srv2ProcessPacket"
0x140074b83  xor     edx, edx
0x140074b85  mov     r8d, 79h ; 'y'
0x140074b8b  call    SRV2_PERF_ENTER_EX
0x140074b90  xor     r8d, r8d
0x140074b93  xor     edx, edx
0x140074b95  mov     rcx, rbx
0x140074b98  call    Srv2CallProviders
0x140074b9d  test    dil, dil
0x140074ba0  jnz     short loc_140074BFA
0x140074ba2  mov     rcx, [rsp+58h+var_18]
0x140074ba7  xor     rcx, rsp; StackCookie
0x140074baa  call    __security_check_cookie
0x140074baf  mov     rbx, [rsp+58h+arg_8]
0x140074bb4  mov     rsi, [rsp+58h+arg_10]
0x140074bb9  add     rsp, 50h
0x140074bbd  pop     rdi
0x140074bbe  retn
0x140074bc0  call    SRV2_PERF_ISSUE_RECEIVE_CORRELATION
0x140074bc5  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x140074bcc  jz      loc_140074B0B
0x140074bd2  movups  xmm0, xmmword ptr [rbx+248h]
0x140074bd9  lea     rcx, [rsp+58h+var_28]
0x140074bde  movups  [rsp+58h+var_28], xmm0
0x140074be3  call    cs:__imp_IoSetActivityIdThread
0x140074bea  nop     dword ptr [rax+rax+00h]
0x140074bef  mov     rsi, rax
0x140074bf2  mov     dil, 1
0x140074bf5  jmp     loc_140074B0B
0x140074bfa  mov     rcx, rsi
0x140074bfd  call    cs:__imp_IoClearActivityIdThread
0x140074c04  nop     dword ptr [rax+rax+00h]
0x140074c09  jmp     short loc_140074BA2
0x140074c0b  cmp     byte ptr [r10+29h], 2
0x140074c10  jb      loc_140074B2B
0x140074c16  mov     rcx, [r10+18h]
0x140074c1a  lea     r8, WPP_42ed7384cb6a3283aec034377101fac6_Traceguids
0x140074c21  mov     edx, 0Ah
0x140074c26  mov     r9, rbx
0x140074c29  call    WPP_SF_q
0x140074c2e  jmp     loc_140074B2B
0x140074c33  call    Srv2InitializeConnectionPassive
0x140074c38  jmp     loc_140074B70
```
