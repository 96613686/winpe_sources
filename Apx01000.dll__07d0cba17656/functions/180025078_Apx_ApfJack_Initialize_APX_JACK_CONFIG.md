# Apx::ApfJack::Initialize(_APX_JACK_CONFIG *)

- ea: `0x180025078`
- end: `0x180025129`
- name: `?Initialize@ApfJack@Apx@@AEAAJPEAU_APX_JACK_CONFIG@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(Apx::ApfJack *__hidden this, struct _APX_JACK_CONFIG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180025130`

## callees

- `0x18000a12c`
- `0x180025078`

## pseudocode

```c
__int64 __fastcall Apx::ApfJack::Initialize(Apx::ApfJack *this, struct _APX_JACK_CONFIG *a2)
{
  bool v4; // zf

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_f8163cda866833e145b9bcd9ddfa387c_Traceguids);
  }
  *(_OWORD *)((char *)this + 20) = *(_OWORD *)((char *)a2 + 24);
  *(_QWORD *)((char *)this + 36) = *((_QWORD *)a2 + 5);
  v4 = (*((_DWORD *)a2 + 2) & 1) == 0;
  *((_DWORD *)this + 4) = *((_DWORD *)a2 + 2) & 1;
  if ( !v4 )
    *((_QWORD *)this + 6) = *(_QWORD *)(*((_QWORD *)a2 + 2) + 8LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_f8163cda866833e145b9bcd9ddfa387c_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180025078  mov     [rsp+arg_0], rbx
0x18002507d  mov     [rsp+arg_8], rsi
0x180025082  push    rdi
0x180025083  sub     rsp, 20h
0x180025087  mov     rbx, rdx
0x18002508a  mov     rdi, rcx
0x18002508d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025094  lea     rsi, WPP_GLOBAL_Control
0x18002509b  cmp     rcx, rsi
0x18002509e  jz      short loc_1800250C1
0x1800250a0  test    byte ptr [rcx+1Ch], 1
0x1800250a4  jz      short loc_1800250C1
0x1800250a6  cmp     byte ptr [rcx+19h], 5
0x1800250aa  jb      short loc_1800250C1
0x1800250ac  mov     rcx, [rcx+10h]
0x1800250b0  lea     r8, WPP_f8163cda866833e145b9bcd9ddfa387c_Traceguids
0x1800250b7  mov     edx, 10h
0x1800250bc  call    WPP_SF_
0x1800250c1  movups  xmm0, xmmword ptr [rbx+18h]
0x1800250c5  movups  xmmword ptr [rdi+14h], xmm0
0x1800250c9  movsd   xmm1, qword ptr [rbx+28h]
0x1800250ce  movsd   qword ptr [rdi+24h], xmm1
0x1800250d3  mov     eax, [rbx+8]
0x1800250d6  and     eax, 1
0x1800250d9  mov     [rdi+10h], eax
0x1800250dc  jz      short loc_1800250EA
0x1800250de  mov     rax, [rbx+10h]
0x1800250e2  mov     rcx, [rax+8]
0x1800250e6  mov     [rdi+30h], rcx
0x1800250ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800250f1  cmp     rcx, rsi
0x1800250f4  jz      short loc_180025117
0x1800250f6  test    byte ptr [rcx+1Ch], 1
0x1800250fa  jz      short loc_180025117
0x1800250fc  cmp     byte ptr [rcx+19h], 5
0x180025100  jb      short loc_180025117
0x180025102  mov     rcx, [rcx+10h]
0x180025106  lea     r8, WPP_f8163cda866833e145b9bcd9ddfa387c_Traceguids
0x18002510d  mov     edx, 11h
0x180025112  call    WPP_SF_
0x180025117  mov     rbx, [rsp+28h+arg_0]
0x18002511c  xor     eax, eax
0x18002511e  mov     rsi, [rsp+28h+arg_8]
0x180025123  add     rsp, 20h
0x180025127  pop     rdi
0x180025128  retn
```
