# Apx::ApfMute::Initialize(_APX_MUTE_CONFIG *)

- ea: `0x18001be94`
- end: `0x18001bf48`
- name: `?Initialize@ApfMute@Apx@@AEAAJPEAU_APX_MUTE_CONFIG@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(Apx::ApfMute *__hidden this, struct _APX_MUTE_CONFIG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001bf50`

## callees

- `0x18000a12c`
- `0x18001be94`

## pseudocode

```c
__int64 __fastcall Apx::ApfMute::Initialize(Apx::ApfMute *this, struct _APX_MUTE_CONFIG *a2)
{
  __int64 v4; // rax
  _OWORD *v5; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_64ae85588b933d5fc12e048f7b1b1b84_Traceguids);
  }
  v4 = *((_QWORD *)a2 + 3);
  *(_OWORD *)((char *)this + 72) = *(_OWORD *)v4;
  *((_QWORD *)this + 11) = *(_QWORD *)(v4 + 16);
  v5 = (_OWORD *)*((_QWORD *)a2 + 1);
  if ( v5 )
    *(_OWORD *)((char *)this + 36) = *v5;
  *((_DWORD *)this + 24) = *((_DWORD *)a2 + 5);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_64ae85588b933d5fc12e048f7b1b1b84_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18001be94  mov     [rsp+arg_0], rbx
0x18001be99  mov     [rsp+arg_8], rsi
0x18001be9e  push    rdi
0x18001be9f  sub     rsp, 20h
0x18001bea3  mov     rdi, rdx
0x18001bea6  mov     rbx, rcx
0x18001bea9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001beb0  lea     rsi, WPP_GLOBAL_Control
0x18001beb7  cmp     rcx, rsi
0x18001beba  jz      short loc_18001BEDD
0x18001bebc  test    byte ptr [rcx+1Ch], 1
0x18001bec0  jz      short loc_18001BEDD
0x18001bec2  cmp     byte ptr [rcx+19h], 5
0x18001bec6  jb      short loc_18001BEDD
0x18001bec8  mov     rcx, [rcx+10h]
0x18001becc  lea     r8, WPP_64ae85588b933d5fc12e048f7b1b1b84_Traceguids
0x18001bed3  mov     edx, 10h
0x18001bed8  call    WPP_SF_
0x18001bedd  mov     rax, [rdi+18h]
0x18001bee1  movups  xmm0, xmmword ptr [rax]
0x18001bee4  movups  xmmword ptr [rbx+48h], xmm0
0x18001bee8  movsd   xmm1, qword ptr [rax+10h]
0x18001beed  movsd   qword ptr [rbx+58h], xmm1
0x18001bef2  mov     rax, [rdi+8]
0x18001bef6  test    rax, rax
0x18001bef9  jz      short loc_18001BF03
0x18001befb  movups  xmm0, xmmword ptr [rax]
0x18001befe  movdqu  xmmword ptr [rbx+24h], xmm0
0x18001bf03  mov     eax, [rdi+14h]
0x18001bf06  mov     [rbx+60h], eax
0x18001bf09  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf10  cmp     rcx, rsi
0x18001bf13  jz      short loc_18001BF36
0x18001bf15  test    byte ptr [rcx+1Ch], 1
0x18001bf19  jz      short loc_18001BF36
0x18001bf1b  cmp     byte ptr [rcx+19h], 5
0x18001bf1f  jb      short loc_18001BF36
0x18001bf21  mov     rcx, [rcx+10h]
0x18001bf25  lea     r8, WPP_64ae85588b933d5fc12e048f7b1b1b84_Traceguids
0x18001bf2c  mov     edx, 11h
0x18001bf31  call    WPP_SF_
0x18001bf36  mov     rbx, [rsp+28h+arg_0]
0x18001bf3b  xor     eax, eax
0x18001bf3d  mov     rsi, [rsp+28h+arg_8]
0x18001bf42  add     rsp, 20h
0x18001bf46  pop     rdi
0x18001bf47  retn
```
