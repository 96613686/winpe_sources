# SecureDmaEnabler_Unmap

- ea: `0x140056908`
- end: `0x1400569ea`
- name: `SecureDmaEnabler_Unmap`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140080730`

## callees

- `0x14001ad0c`
- `0x14001c178`
- `0x140056908`
- `0x140059970`

## import_xrefs

- `ntoskrnl!VslDeleteSecureSection` at `0x14005697b`
- `ntoskrnl!VslDeleteSecureSection` at `0x14005697b`

## pseudocode

```c
__int64 __fastcall SecureDmaEnabler_Unmap(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v4; // rcx
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  int v10; // edx
  __int64 v11; // [rsp+30h] [rbp-48h] BYREF
  __int128 v12; // [rsp+38h] [rbp-40h]
  __int64 v13; // [rsp+48h] [rbp-30h]
  __int64 v14; // [rsp+50h] [rbp-28h]
  __int64 v15; // [rsp+58h] [rbp-20h]

  v2 = *(_QWORD *)(a1 + 16);
  v4 = *(_QWORD *)(a1 + 8);
  v11 = 0;
  v12 = 0;
  v13 = v2;
  v15 = *(_QWORD *)(a2 + 16);
  v14 = 6;
  result = SecureChannel_SendRequestSynchronously(*(_QWORD *)(v4 + 112), &v11, 48, 0, 0);
  v9 = *(_QWORD *)(a2 + 24);
  if ( v9 )
  {
    result = VslDeleteSecureSection(v9, v7, v8);
    if ( (int)result < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 3;
      result = WPP_RECORDER_SF_d(
                 *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
                 v10,
                 18,
                 19,
                 (__int64)WPP_8d19556b374b3e85e4187adf480561f2_Traceguids,
                 result);
    }
  }
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x140056908  mov     r11, rsp
0x14005690b  mov     [r11+18h], rbx
0x14005690f  push    rdi
0x140056910  sub     rsp, 70h
0x140056914  mov     rax, cs:__security_cookie
0x14005691b  xor     rax, rsp
0x14005691e  mov     [rsp+78h+var_18], rax
0x140056923  mov     rax, [rcx+10h]
0x140056927  mov     rdi, rcx
0x14005692a  mov     rcx, [rcx+8]
0x14005692e  xorps   xmm0, xmm0
0x140056931  mov     qword ptr [r11-48h], 0
0x140056939  xor     r9d, r9d
0x14005693c  movdqu  [rsp+78h+var_40], xmm0
0x140056942  mov     [r11-30h], rax
0x140056946  mov     rbx, rdx
0x140056949  mov     rax, [rdx+10h]
0x14005694d  lea     rdx, [r11-48h]
0x140056951  mov     [r11-20h], rax
0x140056955  lea     r8d, [r9+30h]
0x140056959  mov     qword ptr [r11-28h], 6
0x140056961  mov     rcx, [rcx+70h]
0x140056965  mov     dword ptr [rsp+78h+var_58], 0
0x14005696d  call    SecureChannel_SendRequestSynchronously
0x140056972  mov     rcx, [rbx+18h]
0x140056976  test    rcx, rcx
0x140056979  jz      short loc_1400569C4
0x14005697b  call    cs:__imp_VslDeleteSecureSection
0x140056982  nop     dword ptr [rax+rax+00h]
0x140056987  test    eax, eax
0x140056989  jns     short loc_1400569C4
0x14005698b  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140056992  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140056999  jz      short loc_1400569C4
0x14005699b  mov     rcx, [rdi+8]
0x14005699f  mov     r9d, 13h
0x1400569a5  mov     [rsp+78h+var_50], eax
0x1400569a9  mov     dl, 3
0x1400569ab  lea     rax, WPP_8d19556b374b3e85e4187adf480561f2_Traceguids
0x1400569b2  mov     [rsp+78h+var_58], rax
0x1400569b7  mov     rcx, [rcx+48h]
0x1400569bb  lea     r8d, [r9-1]
0x1400569bf  call    WPP_RECORDER_SF_d
0x1400569c4  xorps   xmm0, xmm0
0x1400569c7  movups  xmmword ptr [rbx], xmm0
0x1400569ca  movups  xmmword ptr [rbx+10h], xmm0
0x1400569ce  mov     rcx, [rsp+78h+var_18]
0x1400569d3  xor     rcx, rsp; StackCookie
0x1400569d6  call    __security_check_cookie
0x1400569db  mov     rbx, [rsp+78h+arg_10]
0x1400569e3  add     rsp, 70h
0x1400569e7  pop     rdi
0x1400569e8  retn
```
