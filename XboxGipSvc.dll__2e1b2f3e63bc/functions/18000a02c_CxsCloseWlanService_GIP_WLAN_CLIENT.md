# CxsCloseWlanService(_GIP_WLAN_CLIENT *)

- ea: `0x18000a02c`
- end: `0x18000a0cd`
- name: `?CxsCloseWlanService@@YAXPEAU_GIP_WLAN_CLIENT@@@Z`
- size: `161`
- prototype: `void __fastcall(SC_HANDLE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000aa40`

## callees

- `0x18000a02c`
- `0x18000ba20`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000a073`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000a0b4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000a073`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000a0b4`

## pseudocode

```c
void __fastcall CxsCloseWlanService(SC_HANDLE *a1)
{
  if ( a1[9] )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 24);
    }
    CloseServiceHandle(a1[9]);
    a1[9] = 0;
  }
  if ( a1[10] )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 25);
    }
    CloseServiceHandle(a1[10]);
    a1[10] = 0;
  }
}

```

## disassembly

```asm
0x18000a02c  mov     [rsp+arg_0], rbx
0x18000a031  push    rdi
0x18000a032  sub     rsp, 20h
0x18000a036  mov     r9, [rcx+48h]
0x18000a03a  lea     rdi, WPP_GLOBAL_Control
0x18000a041  mov     rbx, rcx
0x18000a044  test    r9, r9
0x18000a047  jz      short loc_18000A081
0x18000a049  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a050  cmp     rcx, rdi
0x18000a053  jz      short loc_18000A06F
0x18000a055  test    byte ptr [rcx+1Ch], 4
0x18000a059  jz      short loc_18000A06F
0x18000a05b  cmp     byte ptr [rcx+19h], 5
0x18000a05f  jb      short loc_18000A06F
0x18000a061  mov     rcx, [rcx+10h]
0x18000a065  mov     edx, 18h
0x18000a06a  call    WPP_SF_q
0x18000a06f  mov     rcx, [rbx+48h]; hSCObject
0x18000a073  call    cs:__imp_CloseServiceHandle
0x18000a079  mov     qword ptr [rbx+48h], 0
0x18000a081  mov     r9, [rbx+50h]
0x18000a085  test    r9, r9
0x18000a088  jz      short loc_18000A0C2
0x18000a08a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a091  cmp     rcx, rdi
0x18000a094  jz      short loc_18000A0B0
0x18000a096  test    byte ptr [rcx+1Ch], 4
0x18000a09a  jz      short loc_18000A0B0
0x18000a09c  cmp     byte ptr [rcx+19h], 5
0x18000a0a0  jb      short loc_18000A0B0
0x18000a0a2  mov     rcx, [rcx+10h]
0x18000a0a6  mov     edx, 19h
0x18000a0ab  call    WPP_SF_q
0x18000a0b0  mov     rcx, [rbx+50h]; hSCObject
0x18000a0b4  call    cs:__imp_CloseServiceHandle
0x18000a0ba  mov     qword ptr [rbx+50h], 0
0x18000a0c2  mov     rbx, [rsp+28h+arg_0]
0x18000a0c7  add     rsp, 20h
0x18000a0cb  pop     rdi
0x18000a0cc  retn
```
