# CDsmDeviceScan::InitializeRemovalWatcher(ushort const *)

- ea: `0x18000e63c`
- end: `0x18000e76e`
- name: `?InitializeRemovalWatcher@CDsmDeviceScan@@QEAAJPEBG@Z`
- size: `306`
- prototype: `__int64 __fastcall(CDsmDeviceScan *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800191b0`

## callees

- `0x18000e5d8`
- `0x18000e63c`
- `0x180022070`
- `0x180027ba8`
- `0x18002f078`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e71d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e71d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e694`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e6d1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e694`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e6d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6e0`

## pseudocode

```c
__int64 __fastcall CDsmDeviceScan::InitializeRemovalWatcher(CDsmDeviceScan *this, const unsigned __int16 *a2)
{
  signed int ObjectInstance; // ebx
  HANDLE EventW; // rax
  __int64 v6; // rdx
  signed int LastError; // eax
  HANDLE v8; // rax
  signed int v9; // eax
  DWORD v10; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_43d4499022663c6448c6fdf63854fbee_Traceguids, a2);
  ObjectInstance = 0;
  if ( !*((_QWORD *)this + 3) )
  {
    EventW = CreateEventW(0, 1, 1, 0);
    *((_QWORD *)this + 3) = EventW;
    if ( EventW )
      goto LABEL_13;
    LastError = GetLastError();
    ObjectInstance = LastError;
    if ( LastError > 0 )
      ObjectInstance = (unsigned __int16)LastError | 0x80070000;
    if ( ObjectInstance >= 0 )
    {
LABEL_13:
      if ( *((_QWORD *)this + 2) )
        goto LABEL_14;
      v8 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 2) = v8;
      if ( v8 )
        goto LABEL_14;
      v9 = GetLastError();
      ObjectInstance = v9;
      if ( v9 > 0 )
        ObjectInstance = (unsigned __int16)v9 | 0x80070000;
      if ( ObjectInstance >= 0 )
      {
LABEL_14:
        *((_DWORD *)this + 40) = 2;
        ObjectInstance = CDevQuery::QueryObjectInstance(this, v6, a2);
        if ( ObjectInstance >= 0 )
        {
          v10 = WaitForSingleObject(*((HANDLE *)this + 2), 0x2710u);
          if ( v10 )
          {
            ObjectInstance = -2147467259;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_43d4499022663c6448c6fdf63854fbee_Traceguids, v10);
            CDsmDeviceScan::Close(this);
          }
          else
          {
            return 0;
          }
        }
      }
    }
  }
  return (unsigned int)ObjectInstance;
}

```

## disassembly

```asm
0x18000e63c  push    rbx
0x18000e63e  push    rsi
0x18000e63f  push    rdi
0x18000e640  push    r14
0x18000e642  sub     rsp, 38h
0x18000e646  mov     rsi, rdx
0x18000e649  mov     rdi, rcx
0x18000e64c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e653  lea     r14, WPP_GLOBAL_Control
0x18000e65a  cmp     rcx, r14
0x18000e65d  jz      short loc_18000E67D
0x18000e65f  test    byte ptr [rcx+1Ch], 1
0x18000e663  jz      short loc_18000E67D
0x18000e665  mov     rcx, [rcx+10h]
0x18000e669  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x18000e670  mov     edx, 16h
0x18000e675  mov     r9, rsi
0x18000e678  call    WPP_SF_S
0x18000e67d  xor     ebx, ebx
0x18000e67f  cmp     [rdi+18h], rbx
0x18000e683  jnz     loc_18000E762
0x18000e689  lea     edx, [rbx+1]; bManualReset
0x18000e68c  xor     r9d, r9d; lpName
0x18000e68f  mov     r8d, edx; bInitialState
0x18000e692  xor     ecx, ecx; lpEventAttributes
0x18000e694  call    cs:__imp_CreateEventW
0x18000e69a  mov     [rdi+18h], rax
0x18000e69e  test    rax, rax
0x18000e6a1  jnz     short loc_18000E6C0
0x18000e6a3  call    cs:__imp_GetLastError
0x18000e6a9  mov     ebx, eax
0x18000e6ab  test    eax, eax
0x18000e6ad  jle     short loc_18000E6B8
0x18000e6af  movzx   ebx, ax
0x18000e6b2  or      ebx, 80070000h
0x18000e6b8  test    ebx, ebx
0x18000e6ba  js      loc_18000E762
0x18000e6c0  cmp     qword ptr [rdi+10h], 0
0x18000e6c5  jnz     short loc_18000E6F9
0x18000e6c7  xor     r9d, r9d; lpName
0x18000e6ca  xor     r8d, r8d; bInitialState
0x18000e6cd  xor     edx, edx; bManualReset
0x18000e6cf  xor     ecx, ecx; lpEventAttributes
0x18000e6d1  call    cs:__imp_CreateEventW
0x18000e6d7  mov     [rdi+10h], rax
0x18000e6db  test    rax, rax
0x18000e6de  jnz     short loc_18000E6F9
0x18000e6e0  call    cs:__imp_GetLastError
0x18000e6e6  mov     ebx, eax
0x18000e6e8  test    eax, eax
0x18000e6ea  jle     short loc_18000E6F5
0x18000e6ec  movzx   ebx, ax
0x18000e6ef  or      ebx, 80070000h
0x18000e6f5  test    ebx, ebx
0x18000e6f7  js      short loc_18000E762
0x18000e6f9  mov     r8, rsi
0x18000e6fc  mov     dword ptr [rdi+0A0h], 2
0x18000e706  mov     rcx, rdi
0x18000e709  call    ?QueryObjectInstance@CDevQuery@@QEAAJW4_DEV_OBJECT_TYPE@@PEBGHKPEBU_DEVPROPCOMPKEY@@@Z; CDevQuery::QueryObjectInstance(_DEV_OBJECT_TYPE,ushort const *,int,ulong,_DEVPROPCOMPKEY const *)
0x18000e70e  mov     ebx, eax
0x18000e710  test    eax, eax
0x18000e712  js      short loc_18000E762
0x18000e714  mov     rcx, [rdi+10h]; hHandle
0x18000e718  mov     edx, 2710h; dwMilliseconds
0x18000e71d  call    cs:__imp_WaitForSingleObject
0x18000e723  test    eax, eax
0x18000e725  jnz     short loc_18000E72B
0x18000e727  xor     ebx, ebx
0x18000e729  jmp     short loc_18000E762
0x18000e72b  mov     ebx, 80004005h
0x18000e730  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e737  cmp     rcx, r14
0x18000e73a  jz      short loc_18000E75A
0x18000e73c  test    byte ptr [rcx+1Ch], 4
0x18000e740  jz      short loc_18000E75A
0x18000e742  mov     rcx, [rcx+10h]
0x18000e746  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x18000e74d  mov     edx, 17h
0x18000e752  mov     r9d, eax
0x18000e755  call    WPP_SF_d
0x18000e75a  mov     rcx, rdi; this
0x18000e75d  call    ?Close@CDsmDeviceScan@@QEAAXXZ; CDsmDeviceScan::Close(void)
0x18000e762  mov     eax, ebx
0x18000e764  add     rsp, 38h
0x18000e768  pop     r14
0x18000e76a  pop     rdi
0x18000e76b  pop     rsi
0x18000e76c  pop     rbx
0x18000e76d  retn
```
