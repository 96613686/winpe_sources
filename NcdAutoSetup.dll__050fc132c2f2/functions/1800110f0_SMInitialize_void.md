# SMInitialize(void)

- ea: `0x1800110f0`
- end: `0x1800111ed`
- name: `?SMInitialize@@YAJXZ`
- size: `253`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180012de0`

## callees

- `0x18000a644`
- `0x18000a778`
- `0x1800107f0`
- `0x1800110f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011171`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011171`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001115b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001115b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001112f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001112f`

## pseudocode

```c
__int64 SMInitialize(void)
{
  unsigned int v0; // ebx
  signed int LastError; // eax
  _QWORD *v2; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids);
  InitializeCriticalSection(&g_StateMachine);
  dword_18001ADA8 = 0;
  *(_OWORD *)&Block = 0;
  STInitialize();
  hObject = CreateEventW(0, 1, 0, 0);
  if ( hObject )
  {
    v0 = 0;
    goto LABEL_13;
  }
  LastError = GetLastError();
  v0 = LastError;
  if ( LastError > 0 )
    v0 = (unsigned __int16)LastError | 0x80070000;
  if ( (v0 & 0x80000000) == 0 )
    v0 = -2147467259;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_14:
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
        WPP_SF_(v2[2], 12, &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids);
      return v0;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids);
LABEL_13:
    v2 = WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  return v0;
}

```

## disassembly

```asm
0x1800110f0  mov     [rsp+arg_0], rbx
0x1800110f5  push    rdi
0x1800110f6  sub     rsp, 20h
0x1800110fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180011101  lea     rdi, WPP_GLOBAL_Control
0x180011108  cmp     rcx, rdi
0x18001110b  jz      short loc_180011128
0x18001110d  test    byte ptr [rcx+1Ch], 20h
0x180011111  jz      short loc_180011128
0x180011113  mov     rcx, [rcx+10h]
0x180011117  lea     r8, WPP_d77279752c2730a2c88f617b9d74e821_Traceguids
0x18001111e  mov     edx, 0Ah
0x180011123  call    WPP_SF_
0x180011128  lea     rcx, ?g_StateMachine@@3USTATE_MACHINE@@A; lpCriticalSection
0x18001112f  call    cs:__imp_InitializeCriticalSection
0x180011135  xorps   xmm0, xmm0
0x180011138  mov     cs:dword_18001ADA8, 0
0x180011142  movdqa  cs:Block, xmm0
0x18001114a  call    ?STInitialize@@YAXXZ; STInitialize(void)
0x18001114f  xor     r9d, r9d; lpName
0x180011152  xor     r8d, r8d; bInitialState
0x180011155  xor     ecx, ecx; lpEventAttributes
0x180011157  lea     edx, [r9+1]; bManualReset
0x18001115b  call    cs:__imp_CreateEventW
0x180011161  mov     cs:hObject, rax
0x180011168  test    rax, rax
0x18001116b  jz      short loc_180011171
0x18001116d  xor     ebx, ebx
0x18001116f  jmp     short loc_1800111B9
0x180011171  call    cs:__imp_GetLastError
0x180011177  mov     ebx, eax
0x180011179  test    eax, eax
0x18001117b  jle     short loc_180011186
0x18001117d  movzx   ebx, ax
0x180011180  or      ebx, 80070000h
0x180011186  test    ebx, ebx
0x180011188  js      short loc_18001118F
0x18001118a  mov     ebx, 80004005h
0x18001118f  mov     r9d, ebx
0x180011192  mov     rcx, cs:WPP_GLOBAL_Control
0x180011199  cmp     rcx, rdi
0x18001119c  jz      short loc_1800111E0
0x18001119e  test    byte ptr [rcx+1Ch], 2
0x1800111a2  jz      short loc_1800111C0
0x1800111a4  mov     rcx, [rcx+10h]
0x1800111a8  lea     r8, WPP_d77279752c2730a2c88f617b9d74e821_Traceguids
0x1800111af  mov     edx, 0Bh
0x1800111b4  call    WPP_SF_d
0x1800111b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111c0  cmp     rcx, rdi
0x1800111c3  jz      short loc_1800111E0
0x1800111c5  test    byte ptr [rcx+1Ch], 20h
0x1800111c9  jz      short loc_1800111E0
0x1800111cb  mov     rcx, [rcx+10h]
0x1800111cf  lea     r8, WPP_d77279752c2730a2c88f617b9d74e821_Traceguids
0x1800111d6  mov     edx, 0Ch
0x1800111db  call    WPP_SF_
0x1800111e0  mov     eax, ebx
0x1800111e2  mov     rbx, [rsp+28h+arg_0]
0x1800111e7  add     rsp, 20h
0x1800111eb  pop     rdi
0x1800111ec  retn
```
