# CDeviceHandler::~CDeviceHandler(void)

- ea: `0x1800033ec`
- end: `0x1800034b1`
- name: `??1CDeviceHandler@@QEAA@XZ`
- size: `197`
- prototype: `void __fastcall(CDeviceHandler *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000d094`
- `0x1800124dc`

## callees

- `0x1800033ec`
- `0x180008034`
- `0x18000a644`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034aa`

## pseudocode

```c
void __fastcall CDeviceHandler::~CDeviceHandler(CDeviceHandler *this)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
  CDeviceHandler::StopDiscovery(this);
  if ( !*((_DWORD *)this + 2) )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_15;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_12;
    v3 = 14;
    goto LABEL_11;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_15;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v3 = 13;
LABEL_11:
    WPP_SF_(v2[2], v3, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_(v2[2], 15, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
LABEL_15:
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x1800033ec  mov     [rsp+arg_0], rbx
0x1800033f1  push    rdi
0x1800033f2  sub     rsp, 20h
0x1800033f6  mov     rbx, rcx
0x1800033f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003400  lea     rdi, WPP_GLOBAL_Control
0x180003407  cmp     rcx, rdi
0x18000340a  jz      short loc_180003427
0x18000340c  test    byte ptr [rcx+1Ch], 20h
0x180003410  jz      short loc_180003427
0x180003412  mov     rcx, [rcx+10h]
0x180003416  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x18000341d  mov     edx, 0Ch
0x180003422  call    WPP_SF_
0x180003427  mov     rcx, rbx; this
0x18000342a  call    ?StopDiscovery@CDeviceHandler@@QEAAXXZ; CDeviceHandler::StopDiscovery(void)
0x18000342f  cmp     dword ptr [rbx+8], 0
0x180003433  jz      short loc_18000344E
0x180003435  mov     rcx, cs:WPP_GLOBAL_Control
0x18000343c  cmp     rcx, rdi
0x18000343f  jz      short loc_18000349C
0x180003441  test    byte ptr [rcx+1Ch], 8
0x180003445  jz      short loc_18000347C
0x180003447  mov     edx, 0Dh
0x18000344c  jmp     short loc_180003465
0x18000344e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003455  cmp     rcx, rdi
0x180003458  jz      short loc_18000349C
0x18000345a  test    byte ptr [rcx+1Ch], 8
0x18000345e  jz      short loc_18000347C
0x180003460  mov     edx, 0Eh
0x180003465  mov     rcx, [rcx+10h]
0x180003469  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x180003470  call    WPP_SF_
0x180003475  mov     rcx, cs:WPP_GLOBAL_Control
0x18000347c  cmp     rcx, rdi
0x18000347f  jz      short loc_18000349C
0x180003481  test    byte ptr [rcx+1Ch], 20h
0x180003485  jz      short loc_18000349C
0x180003487  mov     rcx, [rcx+10h]
0x18000348b  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x180003492  mov     edx, 0Fh
0x180003497  call    WPP_SF_
0x18000349c  lea     rcx, [rbx+10h]
0x1800034a0  mov     rbx, [rsp+28h+arg_0]
0x1800034a5  add     rsp, 20h
0x1800034a9  pop     rdi
0x1800034aa  jmp     cs:__imp_DeleteCriticalSection
```
