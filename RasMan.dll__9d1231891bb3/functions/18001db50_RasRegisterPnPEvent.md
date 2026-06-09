# RasRegisterPnPEvent

- ea: `0x18001db50`
- end: `0x18001dc57`
- name: `RasRegisterPnPEvent`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001d8b0`
- `0x18001db50`
- `0x180020fd8`
- `0x180021000`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001db98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001db98`

## pseudocode

```c
__int64 __fastcall RasRegisterPnPEvent(__int64 a1, int a2)
{
  DWORD CurrentProcessId; // eax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 526, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      527,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  v5 = RasRegisterPnPCommon(a1, 0, 2, a2);
  v6 = v5;
  if ( !v5 )
    goto LABEL_14;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 528, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
LABEL_14:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 529, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18001db50  mov     [rsp+arg_0], rbx
0x18001db55  mov     [rsp+arg_8], rbp
0x18001db5a  push    rdi
0x18001db5b  sub     rsp, 20h
0x18001db5f  mov     ebx, edx
0x18001db61  mov     rdi, rcx
0x18001db64  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db6b  lea     rbp, WPP_GLOBAL_Control
0x18001db72  cmp     rcx, rbp
0x18001db75  jz      short loc_18001DB98
0x18001db77  test    byte ptr [rcx+1Ch], 40h
0x18001db7b  jz      short loc_18001DB98
0x18001db7d  cmp     byte ptr [rcx+19h], 6
0x18001db81  jb      short loc_18001DB98
0x18001db83  mov     rcx, [rcx+10h]
0x18001db87  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001db8e  mov     edx, 20Eh
0x18001db93  call    WPP_SF_
0x18001db98  call    cs:__imp_GetCurrentProcessId
0x18001db9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dba5  cmp     rcx, rbp
0x18001dba8  jz      short loc_18001DBCE
0x18001dbaa  test    byte ptr [rcx+1Ch], 40h
0x18001dbae  jz      short loc_18001DBCE
0x18001dbb0  cmp     byte ptr [rcx+19h], 5
0x18001dbb4  jb      short loc_18001DBCE
0x18001dbb6  mov     rcx, [rcx+10h]
0x18001dbba  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001dbc1  mov     edx, 20Fh
0x18001dbc6  mov     r9d, eax
0x18001dbc9  call    WPP_SF_d
0x18001dbce  xor     edx, edx
0x18001dbd0  mov     r9d, ebx
0x18001dbd3  mov     rcx, rdi
0x18001dbd6  lea     r8d, [rdx+2]
0x18001dbda  call    RasRegisterPnPCommon
0x18001dbdf  mov     ebx, eax
0x18001dbe1  test    eax, eax
0x18001dbe3  jz      short loc_18001DC15
0x18001dbe5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbec  cmp     rcx, rbp
0x18001dbef  jz      short loc_18001DC45
0x18001dbf1  test    byte ptr [rcx+1Ch], 40h
0x18001dbf5  jz      short loc_18001DC1C
0x18001dbf7  cmp     byte ptr [rcx+19h], 2
0x18001dbfb  jb      short loc_18001DC1C
0x18001dbfd  mov     rcx, [rcx+10h]
0x18001dc01  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001dc08  mov     edx, 210h
0x18001dc0d  mov     r9d, eax
0x18001dc10  call    WPP_SF_d
0x18001dc15  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc1c  cmp     rcx, rbp
0x18001dc1f  jz      short loc_18001DC45
0x18001dc21  test    byte ptr [rcx+1Ch], 40h
0x18001dc25  jz      short loc_18001DC45
0x18001dc27  cmp     byte ptr [rcx+19h], 6
0x18001dc2b  jb      short loc_18001DC45
0x18001dc2d  mov     rcx, [rcx+10h]
0x18001dc31  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001dc38  mov     edx, 211h
0x18001dc3d  mov     r9d, ebx
0x18001dc40  call    WPP_SF_d
0x18001dc45  mov     rbp, [rsp+28h+arg_8]
0x18001dc4a  mov     eax, ebx
0x18001dc4c  mov     rbx, [rsp+28h+arg_0]
0x18001dc51  add     rsp, 20h
0x18001dc55  pop     rdi
0x18001dc56  retn
```
