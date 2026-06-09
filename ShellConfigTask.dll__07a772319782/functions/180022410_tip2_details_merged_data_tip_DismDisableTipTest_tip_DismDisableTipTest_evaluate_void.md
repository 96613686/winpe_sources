# tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::evaluate(void)

- ea: `0x180022410`
- end: `0x180022554`
- name: `?evaluate@?$merged_data@U_tip_DismDisableTipTest@@U1@@details@tip2@@EEAAXXZ`
- size: `324`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180022410`

## string_xrefs

- `0x180022478`: `reason::dism_open_session_failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::details::merged_data<_tip_DismDisableTipTest,_tip_DismDisableTipTest>::evaluate(__int64 a1)
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
    case 4:
      v8 = "reason::dism_disable_feature_failed";
      v9 = 114;
      v4 = "reason::dism_disable_feature_failed";
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
0x180022410  mov     eax, [rcx+110h]
0x180022416  mov     r11d, 2
0x18002241c  mov     r9, rcx
0x18002241f  cmp     eax, r11d
0x180022422  jnz     short loc_18002246F
0x180022424  lea     r8, aReasonDismInit; "reason::dism_initialize_failed"
0x18002242b  mov     al, 72h ; 'r'
0x18002242d  mov     r10, r8
0x180022430  lea     edx, [r11-1]
0x180022434  add     r8, rdx
0x180022437  cmp     al, 3Ah ; ':'
0x180022439  jnz     short loc_18002243E
0x18002243b  mov     r10, r8
0x18002243e  mov     al, [r8]
0x180022441  test    al, al
0x180022443  jnz     short loc_180022434
0x180022445  mov     rax, [rcx+108h]
0x18002244c  cmp     byte ptr [rax+98h], 0
0x180022453  jnz     locret_180022553
0x180022459  mov     byte ptr [rax+98h], 3
0x180022460  mov     [rax+9Ah], dx
0x180022467  mov     [rax+0A0h], r10
0x18002246e  retn
0x18002246f  mov     ecx, 3
0x180022474  cmp     eax, ecx
0x180022476  jnz     short loc_1800224BC
0x180022478  lea     r8, aReasonDismOpen; "reason::dism_open_session_failed"
0x18002247f  mov     al, 72h ; 'r'
0x180022481  mov     r10, r8
0x180022484  lea     edx, [rcx-2]
0x180022487  add     r8, rdx
0x18002248a  cmp     al, 3Ah ; ':'
0x18002248c  jnz     short loc_180022491
0x18002248e  mov     r10, r8
0x180022491  mov     al, [r8]
0x180022494  test    al, al
0x180022496  jnz     short loc_180022487
0x180022498  mov     rax, [r9+108h]
0x18002249f  cmp     byte ptr [rax+98h], 0
0x1800224a6  jnz     locret_180022553
0x1800224ac  mov     [rax+98h], cl
0x1800224b2  mov     [rax+9Ah], r11w
0x1800224ba  jmp     short loc_180022467
0x1800224bc  cmp     eax, 4
0x1800224bf  jnz     short loc_180022505
0x1800224c1  lea     r8, aReasonDismDisa; "reason::dism_disable_feature_failed"
0x1800224c8  mov     al, 72h ; 'r'
0x1800224ca  mov     r10, r8
0x1800224cd  mov     edx, 1
0x1800224d2  add     r8, rdx
0x1800224d5  cmp     al, 3Ah ; ':'
0x1800224d7  jnz     short loc_1800224DC
0x1800224d9  mov     r10, r8
0x1800224dc  mov     al, [r8]
0x1800224df  test    al, al
0x1800224e1  jnz     short loc_1800224D2
0x1800224e3  mov     rax, [r9+108h]
0x1800224ea  cmp     byte ptr [rax+98h], 0
0x1800224f1  jnz     short locret_180022553
0x1800224f3  mov     [rax+98h], cl
0x1800224f9  mov     [rax+9Ah], cx
0x180022500  jmp     loc_180022467
0x180022505  mov     rax, [r9+108h]
0x18002250c  test    dword ptr [rax+38h], 200h
0x180022513  jnz     short loc_18002252F
0x180022515  cmp     byte ptr [rax+98h], 0
0x18002251c  jnz     short locret_180022553
0x18002251e  mov     [rax+98h], cl
0x180022524  mov     word ptr [rax+9Ah], 4001h
0x18002252d  jmp     short loc_180022548
0x18002252f  cmp     byte ptr [rax+98h], 0
0x180022536  jnz     short locret_180022553
0x180022538  mov     byte ptr [rax+98h], 1
0x18002253f  mov     word ptr [rax+9Ah], 8000h
0x180022548  mov     qword ptr [rax+0A0h], 0
0x180022553  retn
```
