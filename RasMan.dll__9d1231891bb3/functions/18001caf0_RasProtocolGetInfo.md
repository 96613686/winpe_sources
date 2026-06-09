# RasProtocolGetInfo

- ea: `0x18001caf0`
- end: `0x18001cbfc`
- name: `RasProtocolGetInfo`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001caf0`
- `0x180021000`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall RasProtocolGetInfo(__int64 a1, __int64 a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 442, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v5 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 443;
LABEL_20:
      WPP_SF_d(v4[2], v6, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
      return v5;
    }
    return v5;
  }
  v7 = SubmitLocalRequest(0x43u, a1, a2);
  v5 = v7;
  if ( v7 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 444, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v6 = 445;
    goto LABEL_20;
  }
  return v5;
}

```

## disassembly

```asm
0x18001caf0  mov     [rsp+arg_0], rbx
0x18001caf5  mov     [rsp+arg_8], rbp
0x18001cafa  push    rdi
0x18001cafb  sub     rsp, 20h
0x18001caff  mov     rdi, rdx
0x18001cb02  mov     rbx, rcx
0x18001cb05  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb0c  lea     rbp, WPP_GLOBAL_Control
0x18001cb13  cmp     rcx, rbp
0x18001cb16  jz      short loc_18001CB3C
0x18001cb18  test    byte ptr [rcx+1Ch], 40h
0x18001cb1c  jz      short loc_18001CB3C
0x18001cb1e  cmp     byte ptr [rcx+19h], 6
0x18001cb22  jb      short loc_18001CB3C
0x18001cb24  mov     rcx, [rcx+10h]
0x18001cb28  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001cb2f  mov     edx, 1BAh
0x18001cb34  mov     r9, rbx
0x18001cb37  call    WPP_SF_q
0x18001cb3c  mov     rcx, rbx
0x18001cb3f  call    ValidatePortHandle
0x18001cb44  test    eax, eax
0x18001cb46  jnz     short loc_18001CB74
0x18001cb48  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb4f  mov     ebx, 259h
0x18001cb54  cmp     rcx, rbp
0x18001cb57  jz      loc_18001CBEA
0x18001cb5d  test    byte ptr [rcx+1Ch], 40h
0x18001cb61  jz      loc_18001CBEA
0x18001cb67  cmp     byte ptr [rcx+19h], 2
0x18001cb6b  jb      short loc_18001CBEA
0x18001cb6d  mov     edx, 1BBh
0x18001cb72  jmp     short loc_18001CBD7
0x18001cb74  mov     ecx, 43h ; 'C'
0x18001cb79  mov     r8, rdi
0x18001cb7c  mov     rdx, rbx
0x18001cb7f  call    SubmitLocalRequest
0x18001cb84  mov     ebx, eax
0x18001cb86  test    eax, eax
0x18001cb88  jz      short loc_18001CBBA
0x18001cb8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb91  cmp     rcx, rbp
0x18001cb94  jz      short loc_18001CBEA
0x18001cb96  test    byte ptr [rcx+1Ch], 40h
0x18001cb9a  jz      short loc_18001CBC1
0x18001cb9c  cmp     byte ptr [rcx+19h], 2
0x18001cba0  jb      short loc_18001CBC1
0x18001cba2  mov     rcx, [rcx+10h]
0x18001cba6  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001cbad  mov     edx, 1BCh
0x18001cbb2  mov     r9d, eax
0x18001cbb5  call    WPP_SF_d
0x18001cbba  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbc1  cmp     rcx, rbp
0x18001cbc4  jz      short loc_18001CBEA
0x18001cbc6  test    byte ptr [rcx+1Ch], 40h
0x18001cbca  jz      short loc_18001CBEA
0x18001cbcc  cmp     byte ptr [rcx+19h], 6
0x18001cbd0  jb      short loc_18001CBEA
0x18001cbd2  mov     edx, 1BDh
0x18001cbd7  mov     rcx, [rcx+10h]
0x18001cbdb  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001cbe2  mov     r9d, ebx
0x18001cbe5  call    WPP_SF_d
0x18001cbea  mov     rbp, [rsp+28h+arg_8]
0x18001cbef  mov     eax, ebx
0x18001cbf1  mov     rbx, [rsp+28h+arg_0]
0x18001cbf6  add     rsp, 20h
0x18001cbfa  pop     rdi
0x18001cbfb  retn
```
