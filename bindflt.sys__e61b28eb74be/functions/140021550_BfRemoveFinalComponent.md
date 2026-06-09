# BfRemoveFinalComponent

- ea: `0x140021550`
- end: `0x14002168a`
- name: `BfRemoveFinalComponent`
- size: `314`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013864`
- `0x140020ff0`
- `0x140023420`

## callees

- `0x140003304`
- `0x140021550`

## pseudocode

```c
__int64 __fastcall BfRemoveFinalComponent(unsigned __int16 *a1, unsigned __int16 a2, __int64 a3)
{
  unsigned __int16 v3; // r11
  __int64 v4; // r10
  unsigned int v6; // edi
  __int64 v7; // rcx
  _WORD *v8; // rax
  int v9; // edx
  unsigned int v10; // ebx
  int v11; // edi
  __int16 v12; // si
  __int16 v13; // dx
  unsigned __int16 v15; // ax

  v3 = *a1;
  v4 = *((_QWORD *)a1 + 1);
  v6 = a2;
  if ( *a1 )
  {
    v7 = (unsigned __int16)((v3 >> 1) - 1);
    v8 = (_WORD *)(v4 + 2 * v7);
    if ( *v8 != 92 )
    {
      v9 = 0;
LABEL_4:
      v10 = -1073741811;
      v11 = (v6 >> 1) - 1;
      while ( 1 )
      {
        if ( (unsigned __int16)v7 <= v11 )
          return v10;
        v12 = *(_WORD *)(v4 + 2LL * (unsigned __int16)v7);
        if ( v12 == 92 )
          break;
        if ( v12 == 58 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v9) = 2;
            WPP_RECORDER_SF_sD(
              WPP_GLOBAL_Control->DeviceExtension,
              v9,
              8,
              20,
              (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
              142);
          }
          return v10;
        }
        if ( !(_WORD)v7 )
        {
          *(_QWORD *)(a3 + 8) = v4;
          v15 = *a1;
          *(_WORD *)a3 = *a1;
          *(_WORD *)(a3 + 2) = v15;
          *a1 = 0;
          return 0;
        }
        LOWORD(v7) = v7 - 1;
        LOWORD(v9) = v9 + 1;
      }
      v13 = 2 * v9;
      *a1 = v3 - v13;
      v10 = 0;
      *(_QWORD *)(a3 + 8) = v4 + 2 + 2LL * (unsigned __int16)v7;
      *(_WORD *)a3 = v13;
      *(_WORD *)(a3 + 2) = v13;
      return v10;
    }
    if ( v3 >> 1 != 1 )
    {
      LOWORD(v7) = (v3 >> 1) - 2;
      v9 = 1;
      goto LABEL_4;
    }
    *(_QWORD *)(a3 + 8) = v8;
  }
  else
  {
    *(_QWORD *)(a3 + 8) = v4;
  }
  *(_DWORD *)a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x140021550  push    rbx
0x140021552  push    rbp
0x140021553  push    rsi
0x140021554  push    rdi
0x140021555  push    r14
0x140021557  sub     rsp, 40h
0x14002155b  movzx   r11d, word ptr [rcx]
0x14002155f  xor     ebp, ebp
0x140021561  mov     r10, [rcx+8]
0x140021565  mov     r9, rcx
0x140021568  movzx   edi, dx
0x14002156b  test    r11w, r11w
0x14002156f  jz      loc_1400215FF
0x140021575  movzx   eax, r11w
0x140021579  lea     r14d, [rbp+1]
0x14002157d  shr     ax, 1
0x140021580  sub     ax, r14w
0x140021584  movzx   ecx, ax
0x140021587  lea     rax, [r10+rcx*2]
0x14002158b  cmp     word ptr [rax], 5Ch ; '\'
0x14002158f  jz      loc_140021621
0x140021595  mov     edx, ebp
0x140021597  shr     edi, 1
0x140021599  mov     ebx, 0C000000Dh
0x14002159e  sub     edi, r14d
0x1400215a1  movzx   eax, cx
0x1400215a4  cmp     eax, edi
0x1400215a6  jle     short loc_1400215F1
0x1400215a8  movzx   eax, cx
0x1400215ab  movzx   esi, word ptr [r10+rax*2]
0x1400215b0  cmp     si, 5Ch ; '\'
0x1400215b4  jz      short loc_1400215CF
0x1400215b6  cmp     si, 3Ah ; ':'
0x1400215ba  jz      short loc_140021639
0x1400215bc  test    cx, cx
0x1400215bf  jz      short loc_14002160A
0x1400215c1  mov     eax, 0FFFFh
0x1400215c6  add     cx, ax
0x1400215c9  add     dx, r14w
0x1400215cd  jmp     short loc_1400215A1
0x1400215cf  add     dx, dx
0x1400215d2  lea     rcx, [r10+2]
0x1400215d6  sub     r11w, dx
0x1400215da  lea     rcx, [rcx+rax*2]
0x1400215de  mov     [r9], r11w
0x1400215e2  mov     ebx, ebp
0x1400215e4  mov     [r8+8], rcx
0x1400215e8  mov     [r8], dx
0x1400215ec  mov     [r8+2], dx
0x1400215f1  mov     eax, ebx
0x1400215f3  add     rsp, 40h
0x1400215f7  pop     r14
0x1400215f9  pop     rdi
0x1400215fa  pop     rsi
0x1400215fb  pop     rbp
0x1400215fc  pop     rbx
0x1400215fd  retn
0x1400215ff  mov     [r8+8], r10
0x140021603  mov     [r8], ebp
0x140021606  xor     eax, eax
0x140021608  jmp     short loc_1400215F3
0x14002160a  mov     [r8+8], r10
0x14002160e  movzx   eax, word ptr [r9]
0x140021612  mov     [r8], ax
0x140021616  mov     [r8+2], ax
0x14002161b  mov     [r9], bp
0x14002161f  jmp     short loc_140021606
0x140021621  test    cx, cx
0x140021624  jnz     short loc_14002162C
0x140021626  mov     [r8+8], rax
0x14002162a  jmp     short loc_140021603
0x14002162c  sub     cx, r14w
0x140021630  movzx   edx, r14w
0x140021634  jmp     loc_140021597
0x140021639  lea     rax, WPP_RECORDER_INITIALIZED
0x140021640  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140021647  jz      short loc_1400215F1
0x140021649  mov     rcx, cs:WPP_GLOBAL_Control
0x140021650  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140021657  mov     r9d, 14h
0x14002165d  mov     [rsp+68h+var_38], 48Eh
0x140021665  mov     [rsp+68h+var_40], rax
0x14002166a  mov     dl, 2
0x14002166c  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x140021673  mov     rcx, [rcx+40h]
0x140021677  lea     r8d, [r9-0Ch]
0x14002167b  mov     [rsp+68h+var_48], rax
0x140021680  call    WPP_RECORDER_SF_sD
0x140021685  jmp     loc_1400215F1
```
