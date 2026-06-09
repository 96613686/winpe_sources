# RasProtocolEnum

- ea: `0x18001ca10`
- end: `0x18001cadc`
- name: `RasProtocolEnum`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x18001ca10`
- `0x180020fd8`
- `0x180021000`

## pseudocode

```c
__int64 __fastcall RasProtocolEnum(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 245, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v6 = SubmitLocalRequest(0x18u, a2, a1, a3);
  v7 = v6;
  if ( !v6 )
    goto LABEL_10;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 246, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
LABEL_10:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 247, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18001ca10  push    rbx
0x18001ca12  push    rsi
0x18001ca13  push    rdi
0x18001ca14  push    r14
0x18001ca16  sub     rsp, 28h
0x18001ca1a  mov     rbx, r8
0x18001ca1d  mov     rdi, rdx
0x18001ca20  mov     rsi, rcx
0x18001ca23  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca2a  lea     r14, WPP_GLOBAL_Control
0x18001ca31  cmp     rcx, r14
0x18001ca34  jz      short loc_18001CA57
0x18001ca36  test    byte ptr [rcx+1Ch], 40h
0x18001ca3a  jz      short loc_18001CA57
0x18001ca3c  cmp     byte ptr [rcx+19h], 6
0x18001ca40  jb      short loc_18001CA57
0x18001ca42  mov     rcx, [rcx+10h]
0x18001ca46  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ca4d  mov     edx, 0F5h
0x18001ca52  call    WPP_SF_
0x18001ca57  mov     ecx, 18h
0x18001ca5c  mov     r9, rbx
0x18001ca5f  mov     r8, rsi
0x18001ca62  mov     rdx, rdi
0x18001ca65  call    SubmitLocalRequest
0x18001ca6a  mov     ebx, eax
0x18001ca6c  test    eax, eax
0x18001ca6e  jz      short loc_18001CAA0
0x18001ca70  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca77  cmp     rcx, r14
0x18001ca7a  jz      short loc_18001CAD0
0x18001ca7c  test    byte ptr [rcx+1Ch], 40h
0x18001ca80  jz      short loc_18001CAA7
0x18001ca82  cmp     byte ptr [rcx+19h], 2
0x18001ca86  jb      short loc_18001CAA7
0x18001ca88  mov     rcx, [rcx+10h]
0x18001ca8c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ca93  mov     edx, 0F6h
0x18001ca98  mov     r9d, eax
0x18001ca9b  call    WPP_SF_d
0x18001caa0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001caa7  cmp     rcx, r14
0x18001caaa  jz      short loc_18001CAD0
0x18001caac  test    byte ptr [rcx+1Ch], 40h
0x18001cab0  jz      short loc_18001CAD0
0x18001cab2  cmp     byte ptr [rcx+19h], 6
0x18001cab6  jb      short loc_18001CAD0
0x18001cab8  mov     rcx, [rcx+10h]
0x18001cabc  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001cac3  mov     edx, 0F7h
0x18001cac8  mov     r9d, ebx
0x18001cacb  call    WPP_SF_d
0x18001cad0  mov     eax, ebx
0x18001cad2  add     rsp, 28h
0x18001cad6  pop     r14
0x18001cad8  pop     rdi
0x18001cad9  pop     rsi
0x18001cada  pop     rbx
0x18001cadb  retn
```
