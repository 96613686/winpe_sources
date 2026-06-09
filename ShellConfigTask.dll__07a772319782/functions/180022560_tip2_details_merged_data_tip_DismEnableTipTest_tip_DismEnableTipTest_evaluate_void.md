# tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::evaluate(void)

- ea: `0x180022560`
- end: `0x1800226a4`
- name: `?evaluate@?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@EEAAXXZ`
- size: `324`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180022560`

## string_xrefs

- `0x1800225c8`: `reason::dism_open_session_failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::evaluate(__int64 a1)
{
  int v1; // eax
  const char *v2; // r8
  char v3; // al
  const char *v4; // r10
  __int64 result; // rax
  const char *v6; // r8
  char v7; // al
  const char *v8; // r8
  char v9; // al

  v1 = *(_DWORD *)(a1 + 272);
  switch ( v1 )
  {
    case 2:
      v2 = "reason::dism_initialize_failed";
      v3 = 114;
      v4 = "reason::dism_initialize_failed";
      do
      {
        ++v2;
        if ( v3 == 58 )
          v4 = v2;
        v3 = *v2;
      }
      while ( *v2 );
      result = *(_QWORD *)(a1 + 264);
      if ( !*(_BYTE *)(result + 152) )
      {
        *(_BYTE *)(result + 152) = 3;
        *(_WORD *)(result + 154) = 1;
LABEL_8:
        *(_QWORD *)(result + 160) = v4;
      }
      break;
    case 3:
      v6 = "reason::dism_open_session_failed";
      v7 = 114;
      v4 = "reason::dism_open_session_failed";
      do
      {
        ++v6;
        if ( v7 == 58 )
          v4 = v6;
        v7 = *v6;
      }
      while ( *v6 );
      result = *(_QWORD *)(a1 + 264);
      if ( !*(_BYTE *)(result + 152) )
      {
        *(_BYTE *)(result + 152) = 3;
        *(_WORD *)(result + 154) = 2;
        goto LABEL_8;
      }
      break;
    case 5:
      v8 = "reason::dism_enable_feature_failed";
      v9 = 114;
      v4 = "reason::dism_enable_feature_failed";
      do
      {
        ++v8;
        if ( v9 == 58 )
          v4 = v8;
        v9 = *v8;
      }
      while ( *v8 );
      result = *(_QWORD *)(a1 + 264);
      if ( !*(_BYTE *)(result + 152) )
      {
        *(_BYTE *)(result + 152) = 3;
        *(_WORD *)(result + 154) = 3;
        goto LABEL_8;
      }
      break;
    default:
      result = *(_QWORD *)(a1 + 264);
      if ( (*(_DWORD *)(result + 56) & 0x200) != 0 )
      {
        if ( *(_BYTE *)(result + 152) )
          return result;
        *(_BYTE *)(result + 152) = 1;
        *(_WORD *)(result + 154) = 0x8000;
      }
      else
      {
        if ( *(_BYTE *)(result + 152) )
          return result;
        *(_BYTE *)(result + 152) = 3;
        *(_WORD *)(result + 154) = 16385;
      }
      *(_QWORD *)(result + 160) = 0;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x180022560  mov     eax, [rcx+110h]
0x180022566  mov     r11d, 2
0x18002256c  mov     r9, rcx
0x18002256f  cmp     eax, r11d
0x180022572  jnz     short loc_1800225BF
0x180022574  lea     r8, aReasonDismInit; "reason::dism_initialize_failed"
0x18002257b  mov     al, 72h ; 'r'
0x18002257d  mov     r10, r8
0x180022580  lea     edx, [r11-1]
0x180022584  add     r8, rdx
0x180022587  cmp     al, 3Ah ; ':'
0x180022589  jnz     short loc_18002258E
0x18002258b  mov     r10, r8
0x18002258e  mov     al, [r8]
0x180022591  test    al, al
0x180022593  jnz     short loc_180022584
0x180022595  mov     rax, [rcx+108h]
0x18002259c  cmp     byte ptr [rax+98h], 0
0x1800225a3  jnz     locret_1800226A3
0x1800225a9  mov     byte ptr [rax+98h], 3
0x1800225b0  mov     [rax+9Ah], dx
0x1800225b7  mov     [rax+0A0h], r10
0x1800225be  retn
0x1800225bf  mov     ecx, 3
0x1800225c4  cmp     eax, ecx
0x1800225c6  jnz     short loc_18002260C
0x1800225c8  lea     r8, aReasonDismOpen; "reason::dism_open_session_failed"
0x1800225cf  mov     al, 72h ; 'r'
0x1800225d1  mov     r10, r8
0x1800225d4  lea     edx, [rcx-2]
0x1800225d7  add     r8, rdx
0x1800225da  cmp     al, 3Ah ; ':'
0x1800225dc  jnz     short loc_1800225E1
0x1800225de  mov     r10, r8
0x1800225e1  mov     al, [r8]
0x1800225e4  test    al, al
0x1800225e6  jnz     short loc_1800225D7
0x1800225e8  mov     rax, [r9+108h]
0x1800225ef  cmp     byte ptr [rax+98h], 0
0x1800225f6  jnz     locret_1800226A3
0x1800225fc  mov     [rax+98h], cl
0x180022602  mov     [rax+9Ah], r11w
0x18002260a  jmp     short loc_1800225B7
0x18002260c  cmp     eax, 5
0x18002260f  jnz     short loc_180022655
0x180022611  lea     r8, aReasonDismEnab; "reason::dism_enable_feature_failed"
0x180022618  mov     al, 72h ; 'r'
0x18002261a  mov     r10, r8
0x18002261d  mov     edx, 1
0x180022622  add     r8, rdx
0x180022625  cmp     al, 3Ah ; ':'
0x180022627  jnz     short loc_18002262C
0x180022629  mov     r10, r8
0x18002262c  mov     al, [r8]
0x18002262f  test    al, al
0x180022631  jnz     short loc_180022622
0x180022633  mov     rax, [r9+108h]
0x18002263a  cmp     byte ptr [rax+98h], 0
0x180022641  jnz     short locret_1800226A3
0x180022643  mov     [rax+98h], cl
0x180022649  mov     [rax+9Ah], cx
0x180022650  jmp     loc_1800225B7
0x180022655  mov     rax, [r9+108h]
0x18002265c  test    dword ptr [rax+38h], 200h
0x180022663  jnz     short loc_18002267F
0x180022665  cmp     byte ptr [rax+98h], 0
0x18002266c  jnz     short locret_1800226A3
0x18002266e  mov     [rax+98h], cl
0x180022674  mov     word ptr [rax+9Ah], 4001h
0x18002267d  jmp     short loc_180022698
0x18002267f  cmp     byte ptr [rax+98h], 0
0x180022686  jnz     short locret_1800226A3
0x180022688  mov     byte ptr [rax+98h], 1
0x18002268f  mov     word ptr [rax+9Ah], 8000h
0x180022698  mov     qword ptr [rax+0A0h], 0
0x1800226a3  retn
```
