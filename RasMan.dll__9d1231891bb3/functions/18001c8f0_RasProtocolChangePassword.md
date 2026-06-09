# RasProtocolChangePassword

- ea: `0x18001c8f0`
- end: `0x18001ca05`
- name: `RasProtocolChangePassword`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001c8f0`
- `0x180021000`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall RasProtocolChangePassword(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  PVOID *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 438, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v9 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 439;
LABEL_20:
      WPP_SF_d(v8[2], v10, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
      return v9;
    }
    return v9;
  }
  v11 = SubmitLocalRequest(0x44u, a1, a2, a3, a4);
  v9 = v11;
  if ( v11 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 440, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    v10 = 441;
    goto LABEL_20;
  }
  return v9;
}

```

## disassembly

```asm
0x18001c8f0  push    rbx
0x18001c8f2  push    rbp
0x18001c8f3  push    rsi
0x18001c8f4  push    rdi
0x18001c8f5  push    r15
0x18001c8f7  sub     rsp, 30h
0x18001c8fb  mov     rdi, r9
0x18001c8fe  mov     rsi, r8
0x18001c901  mov     rbp, rdx
0x18001c904  mov     rbx, rcx
0x18001c907  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c90e  lea     r15, WPP_GLOBAL_Control
0x18001c915  cmp     rcx, r15
0x18001c918  jz      short loc_18001C93E
0x18001c91a  test    byte ptr [rcx+1Ch], 40h
0x18001c91e  jz      short loc_18001C93E
0x18001c920  cmp     byte ptr [rcx+19h], 6
0x18001c924  jb      short loc_18001C93E
0x18001c926  mov     rcx, [rcx+10h]
0x18001c92a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c931  mov     edx, 1B6h
0x18001c936  mov     r9, rbx
0x18001c939  call    WPP_SF_q
0x18001c93e  mov     rcx, rbx
0x18001c941  call    ValidatePortHandle
0x18001c946  test    eax, eax
0x18001c948  jnz     short loc_18001C97A
0x18001c94a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c951  mov     ebx, 259h
0x18001c956  cmp     rcx, r15
0x18001c959  jz      loc_18001C9F8
0x18001c95f  test    byte ptr [rcx+1Ch], 40h
0x18001c963  jz      loc_18001C9F8
0x18001c969  cmp     byte ptr [rcx+19h], 2
0x18001c96d  jb      loc_18001C9F8
0x18001c973  mov     edx, 1B7h
0x18001c978  jmp     short loc_18001C9E5
0x18001c97a  mov     ecx, 44h ; 'D'
0x18001c97f  mov     [rsp+58h+var_38], rdi
0x18001c984  mov     r9, rsi
0x18001c987  mov     r8, rbp
0x18001c98a  mov     rdx, rbx
0x18001c98d  call    SubmitLocalRequest
0x18001c992  mov     ebx, eax
0x18001c994  test    eax, eax
0x18001c996  jz      short loc_18001C9C8
0x18001c998  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c99f  cmp     rcx, r15
0x18001c9a2  jz      short loc_18001C9F8
0x18001c9a4  test    byte ptr [rcx+1Ch], 40h
0x18001c9a8  jz      short loc_18001C9CF
0x18001c9aa  cmp     byte ptr [rcx+19h], 2
0x18001c9ae  jb      short loc_18001C9CF
0x18001c9b0  mov     rcx, [rcx+10h]
0x18001c9b4  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c9bb  mov     edx, 1B8h
0x18001c9c0  mov     r9d, eax
0x18001c9c3  call    WPP_SF_d
0x18001c9c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c9cf  cmp     rcx, r15
0x18001c9d2  jz      short loc_18001C9F8
0x18001c9d4  test    byte ptr [rcx+1Ch], 40h
0x18001c9d8  jz      short loc_18001C9F8
0x18001c9da  cmp     byte ptr [rcx+19h], 6
0x18001c9de  jb      short loc_18001C9F8
0x18001c9e0  mov     edx, 1B9h
0x18001c9e5  mov     rcx, [rcx+10h]
0x18001c9e9  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c9f0  mov     r9d, ebx
0x18001c9f3  call    WPP_SF_d
0x18001c9f8  mov     eax, ebx
0x18001c9fa  add     rsp, 30h
0x18001c9fe  pop     r15
0x18001ca00  pop     rdi
0x18001ca01  pop     rsi
0x18001ca02  pop     rbp
0x18001ca03  pop     rbx
0x18001ca04  retn
```
