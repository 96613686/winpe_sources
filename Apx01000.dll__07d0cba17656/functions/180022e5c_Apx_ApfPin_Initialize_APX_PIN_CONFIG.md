# Apx::ApfPin::Initialize(_APX_PIN_CONFIG *)

- ea: `0x180022e5c`
- end: `0x180022f1e`
- name: `?Initialize@ApfPin@Apx@@AEAAJPEAU_APX_PIN_CONFIG@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(Apx::ApfPin *__hidden this, struct _APX_PIN_CONFIG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180023274`

## callees

- `0x18000a12c`
- `0x180022e5c`

## pseudocode

```c
__int64 __fastcall Apx::ApfPin::Initialize(Apx::ApfPin *this, struct _APX_PIN_CONFIG *a2)
{
  _OWORD *v4; // rax
  _OWORD *v5; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b80f8302e70934d41d7f826282614d49_Traceguids);
  }
  *((_DWORD *)this + 14) = *((_DWORD *)a2 + 2);
  *((_DWORD *)this + 15) = *((_DWORD *)a2 + 3);
  *((_DWORD *)this + 16) = *((_DWORD *)a2 + 4);
  *((_DWORD *)this + 25) = *((_DWORD *)a2 + 10);
  v4 = (_OWORD *)*((_QWORD *)a2 + 3);
  if ( v4 )
    *(_OWORD *)((char *)this + 68) = *v4;
  v5 = (_OWORD *)*((_QWORD *)a2 + 4);
  if ( v5 )
    *(_OWORD *)((char *)this + 84) = *v5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b80f8302e70934d41d7f826282614d49_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180022e5c  mov     [rsp+arg_0], rbx
0x180022e61  mov     [rsp+arg_8], rsi
0x180022e66  push    rdi
0x180022e67  sub     rsp, 20h
0x180022e6b  mov     rdi, rdx
0x180022e6e  mov     rbx, rcx
0x180022e71  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e78  lea     rsi, WPP_GLOBAL_Control
0x180022e7f  cmp     rcx, rsi
0x180022e82  jz      short loc_180022EA5
0x180022e84  test    byte ptr [rcx+1Ch], 1
0x180022e88  jz      short loc_180022EA5
0x180022e8a  cmp     byte ptr [rcx+19h], 5
0x180022e8e  jb      short loc_180022EA5
0x180022e90  mov     rcx, [rcx+10h]
0x180022e94  lea     r8, WPP_b80f8302e70934d41d7f826282614d49_Traceguids
0x180022e9b  mov     edx, 11h
0x180022ea0  call    WPP_SF_
0x180022ea5  mov     eax, [rdi+8]
0x180022ea8  mov     [rbx+38h], eax
0x180022eab  mov     eax, [rdi+0Ch]
0x180022eae  mov     [rbx+3Ch], eax
0x180022eb1  mov     eax, [rdi+10h]
0x180022eb4  mov     [rbx+40h], eax
0x180022eb7  mov     eax, [rdi+28h]
0x180022eba  mov     [rbx+64h], eax
0x180022ebd  mov     rax, [rdi+18h]
0x180022ec1  test    rax, rax
0x180022ec4  jz      short loc_180022ECE
0x180022ec6  movups  xmm0, xmmword ptr [rax]
0x180022ec9  movdqu  xmmword ptr [rbx+44h], xmm0
0x180022ece  mov     rax, [rdi+20h]
0x180022ed2  test    rax, rax
0x180022ed5  jz      short loc_180022EDF
0x180022ed7  movups  xmm0, xmmword ptr [rax]
0x180022eda  movdqu  xmmword ptr [rbx+54h], xmm0
0x180022edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ee6  cmp     rcx, rsi
0x180022ee9  jz      short loc_180022F0C
0x180022eeb  test    byte ptr [rcx+1Ch], 1
0x180022eef  jz      short loc_180022F0C
0x180022ef1  cmp     byte ptr [rcx+19h], 5
0x180022ef5  jb      short loc_180022F0C
0x180022ef7  mov     rcx, [rcx+10h]
0x180022efb  lea     r8, WPP_b80f8302e70934d41d7f826282614d49_Traceguids
0x180022f02  mov     edx, 12h
0x180022f07  call    WPP_SF_
0x180022f0c  mov     rbx, [rsp+28h+arg_0]
0x180022f11  xor     eax, eax
0x180022f13  mov     rsi, [rsp+28h+arg_8]
0x180022f18  add     rsp, 20h
0x180022f1c  pop     rdi
0x180022f1d  retn
```
