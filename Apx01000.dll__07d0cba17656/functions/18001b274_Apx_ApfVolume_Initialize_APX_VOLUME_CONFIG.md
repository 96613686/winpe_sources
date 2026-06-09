# Apx::ApfVolume::Initialize(_APX_VOLUME_CONFIG *)

- ea: `0x18001b274`
- end: `0x18001b33a`
- name: `?Initialize@ApfVolume@Apx@@AEAAJPEAU_APX_VOLUME_CONFIG@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(Apx::ApfVolume *__hidden this, struct _APX_VOLUME_CONFIG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001b340`

## callees

- `0x18000a12c`
- `0x18001b274`

## pseudocode

```c
__int64 __fastcall Apx::ApfVolume::Initialize(Apx::ApfVolume *this, struct _APX_VOLUME_CONFIG *a2)
{
  __int64 v4; // rax
  _OWORD *v5; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_148a2d0fd9843186e17fb739fb0326db_Traceguids);
  }
  v4 = *((_QWORD *)a2 + 5);
  *(_OWORD *)((char *)this + 72) = *(_OWORD *)v4;
  *((_QWORD *)this + 11) = *(_QWORD *)(v4 + 16);
  v5 = (_OWORD *)*((_QWORD *)a2 + 1);
  if ( v5 )
    *(_OWORD *)((char *)this + 36) = *v5;
  *((_DWORD *)this + 24) = *((_DWORD *)a2 + 5);
  *((_DWORD *)this + 25) = *((_DWORD *)a2 + 7);
  *((_DWORD *)this + 26) = *((_DWORD *)a2 + 6);
  *((_DWORD *)this + 27) = *((_DWORD *)a2 + 8);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_148a2d0fd9843186e17fb739fb0326db_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18001b274  mov     [rsp+arg_0], rbx
0x18001b279  mov     [rsp+arg_8], rsi
0x18001b27e  push    rdi
0x18001b27f  sub     rsp, 20h
0x18001b283  mov     rdi, rdx
0x18001b286  mov     rbx, rcx
0x18001b289  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b290  lea     rsi, WPP_GLOBAL_Control
0x18001b297  cmp     rcx, rsi
0x18001b29a  jz      short loc_18001B2BD
0x18001b29c  test    byte ptr [rcx+1Ch], 1
0x18001b2a0  jz      short loc_18001B2BD
0x18001b2a2  cmp     byte ptr [rcx+19h], 5
0x18001b2a6  jb      short loc_18001B2BD
0x18001b2a8  mov     rcx, [rcx+10h]
0x18001b2ac  lea     r8, WPP_148a2d0fd9843186e17fb739fb0326db_Traceguids
0x18001b2b3  mov     edx, 10h
0x18001b2b8  call    WPP_SF_
0x18001b2bd  mov     rax, [rdi+28h]
0x18001b2c1  movups  xmm0, xmmword ptr [rax]
0x18001b2c4  movups  xmmword ptr [rbx+48h], xmm0
0x18001b2c8  movsd   xmm1, qword ptr [rax+10h]
0x18001b2cd  movsd   qword ptr [rbx+58h], xmm1
0x18001b2d2  mov     rax, [rdi+8]
0x18001b2d6  test    rax, rax
0x18001b2d9  jz      short loc_18001B2E3
0x18001b2db  movups  xmm0, xmmword ptr [rax]
0x18001b2de  movdqu  xmmword ptr [rbx+24h], xmm0
0x18001b2e3  mov     eax, [rdi+14h]
0x18001b2e6  mov     [rbx+60h], eax
0x18001b2e9  mov     eax, [rdi+1Ch]
0x18001b2ec  mov     [rbx+64h], eax
0x18001b2ef  mov     eax, [rdi+18h]
0x18001b2f2  mov     [rbx+68h], eax
0x18001b2f5  mov     eax, [rdi+20h]
0x18001b2f8  mov     [rbx+6Ch], eax
0x18001b2fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b302  cmp     rcx, rsi
0x18001b305  jz      short loc_18001B328
0x18001b307  test    byte ptr [rcx+1Ch], 1
0x18001b30b  jz      short loc_18001B328
0x18001b30d  cmp     byte ptr [rcx+19h], 5
0x18001b311  jb      short loc_18001B328
0x18001b313  mov     rcx, [rcx+10h]
0x18001b317  lea     r8, WPP_148a2d0fd9843186e17fb739fb0326db_Traceguids
0x18001b31e  mov     edx, 11h
0x18001b323  call    WPP_SF_
0x18001b328  mov     rbx, [rsp+28h+arg_0]
0x18001b32d  xor     eax, eax
0x18001b32f  mov     rsi, [rsp+28h+arg_8]
0x18001b334  add     rsp, 20h
0x18001b338  pop     rdi
0x18001b339  retn
```
