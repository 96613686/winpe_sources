# WciSetupFilter

- ea: `0x180024f94`
- end: `0x180025143`
- name: `WciSetupFilter`
- size: `431`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, __int64, DWORD BytesReturned)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001ae40`

## callees

- `0x180024d94`
- `0x180024f94`
- `0x18002514c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180024fd9`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180024fd9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800250cf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800250de`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800250f5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025109`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800250cf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800250de`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800250f5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025109`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002511f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002511f`
- `FLTLIB!FilterConnectCommunicationPort` at `0x180025065`
- `FLTLIB!FilterConnectCommunicationPort` at `0x180025065`
- `FLTLIB!FilterSendMessage` at `0x180025093`
- `FLTLIB!FilterSendMessage` at `0x180025093`
- `ntdll!RtlNtStatusToDosError` at `0x1800250ac`
- `ntdll!RtlNtStatusToDosError` at `0x1800250ac`

## pseudocode

```c
__int64 __fastcall WciSetupFilter(__int64 a1, __int64 a2, const WCHAR *a3, __int64 a4, DWORD BytesReturned)
{
  _DWORD *v5; // rdi
  void **v8; // rax
  void **v9; // rsi
  int RootTokens; // ebx
  int v12; // r9d
  int v13; // eax
  NTSTATUS v14; // ecx
  signed int v15; // eax
  int lpSecurityAttributes; // [rsp+20h] [rbp-40h]
  int hPort; // [rsp+28h] [rbp-38h]
  int hPorta; // [rsp+28h] [rbp-38h]
  int v19; // [rsp+30h] [rbp-30h]
  LPVOID lpInBuffer; // [rsp+50h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-8h] BYREF
  DWORD dwOutBufferSize; // [rsp+88h] [rbp+28h] BYREF

  v5 = 0;
  dwOutBufferSize = 0;
  lpInBuffer = 0;
  hObject = (HANDLE)-1LL;
  BytesReturned = 0;
  v8 = (void **)calloc(8u, 1u);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  RootTokens = WcAttachFilterAndGetRootTokens(a3, a4, hPort, v19, (__int64)v8);
  if ( RootTokens >= 0 )
  {
    v13 = WcpConstructContainerInfoMessage(
            0,
            a4,
            (_DWORD)v9,
            v12,
            lpSecurityAttributes,
            hPorta,
            (__int64)&dwOutBufferSize,
            (__int64)&lpInBuffer);
    v5 = lpInBuffer;
    RootTokens = v13;
    if ( !v13 )
    {
      *(_DWORD *)lpInBuffer = 0;
      RootTokens = FilterConnectCommunicationPort(L"\\WcifsPort", 0, 0, 0, 0, &hObject);
      if ( !RootTokens )
      {
        RootTokens = FilterSendMessage(hObject, v5, dwOutBufferSize, v5, dwOutBufferSize, &BytesReturned);
        if ( !RootTokens )
        {
          v14 = v5[2];
          if ( v14 < 0 )
          {
            v15 = RtlNtStatusToDosError(v14);
            RootTokens = v15;
            if ( v15 > 0 )
              RootTokens = (unsigned __int16)v15 | 0x80070000;
          }
        }
      }
    }
  }
  if ( *v9 )
    free(*v9);
  free(v9);
  if ( v5 )
    free(v5);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return (unsigned int)RootTokens;
}

```

## disassembly

```asm
0x180024f94  mov     rax, rsp
0x180024f97  mov     [rax+18h], rbx
0x180024f9b  mov     [rax+20h], rsi
0x180024f9f  mov     [rax+10h], edx
0x180024fa2  mov     [rax+8], rcx
0x180024fa6  push    rbp
0x180024fa7  push    rdi
0x180024fa8  push    r15
0x180024faa  mov     rbp, rsp
0x180024fad  sub     rsp, 60h
0x180024fb1  xor     edi, edi
0x180024fb3  mov     [rbp+dwOutBufferSize], 0
0x180024fba  mov     r15, r9
0x180024fbd  mov     [rbp+lpInBuffer], rdi
0x180024fc1  mov     rbx, r8
0x180024fc4  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x180024fcc  mov     [rbp+BytesReturned], edi
0x180024fcf  lea     edx, [rdi+1]; Size
0x180024fd2  mov     [rbp+Block], rdi
0x180024fd6  lea     ecx, [rdi+8]; Count
0x180024fd9  call    cs:__imp_calloc
0x180024fe0  nop     dword ptr [rax+rax+00h]
0x180024fe5  mov     rsi, rax
0x180024fe8  test    rax, rax
0x180024feb  jnz     short loc_180024FF7
0x180024fed  mov     eax, 8007000Eh
0x180024ff2  jmp     loc_18002512D
0x180024ff7  mov     [rsp+60h+var_28], rsi; __int64
0x180024ffc  lea     r8, [rbp+Block]
0x180025000  mov     rcx, rbx; lpFileName
0x180025003  mov     [rsp+60h+lpSecurityAttributes], r15; __int64
0x180025008  call    WcAttachFilterAndGetRootTokens
0x18002500d  mov     ebx, eax
0x18002500f  test    eax, eax
0x180025011  js      loc_1800250C7
0x180025017  mov     rcx, [rbp+Block]
0x18002501b  lea     rax, [rbp+lpInBuffer]
0x18002501f  mov     [rsp+60h+var_28], rax
0x180025024  mov     r8, rsi
0x180025027  lea     rax, [rbp+dwOutBufferSize]
0x18002502b  mov     rdx, r15
0x18002502e  mov     [rsp+60h+var_30], rax
0x180025033  call    WcpConstructContainerInfoMessage
0x180025038  mov     rdi, [rbp+lpInBuffer]
0x18002503c  mov     ebx, eax
0x18002503e  test    eax, eax
0x180025040  jnz     loc_1800250C7
0x180025046  mov     [rdi], eax
0x180025048  lea     rcx, PortName; "\\WcifsPort"
0x18002504f  lea     rax, [rbp+hObject]
0x180025053  xor     r9d, r9d; wSizeOfContext
0x180025056  mov     [rsp+60h+hPort], rax; hPort
0x18002505b  xor     r8d, r8d; lpContext
0x18002505e  xor     edx, edx; dwOptions
0x180025060  mov     [rsp+60h+lpSecurityAttributes], r9; lpSecurityAttributes
0x180025065  call    cs:__imp_FilterConnectCommunicationPort
0x18002506c  nop     dword ptr [rax+rax+00h]
0x180025071  mov     ebx, eax
0x180025073  test    eax, eax
0x180025075  jnz     short loc_1800250C7
0x180025077  mov     r8d, [rbp+dwOutBufferSize]; dwInBufferSize
0x18002507b  lea     rax, [rbp+BytesReturned]
0x18002507f  mov     rcx, [rbp+hObject]; hPort
0x180025083  mov     r9, rdi; lpOutBuffer
0x180025086  mov     [rsp+60h+hPort], rax; lpBytesReturned
0x18002508b  mov     rdx, rdi; lpInBuffer
0x18002508e  mov     dword ptr [rsp+60h+lpSecurityAttributes], r8d; dwOutBufferSize
0x180025093  call    cs:__imp_FilterSendMessage
0x18002509a  nop     dword ptr [rax+rax+00h]
0x18002509f  mov     ebx, eax
0x1800250a1  test    eax, eax
0x1800250a3  jnz     short loc_1800250C7
0x1800250a5  mov     ecx, [rdi+8]; Status
0x1800250a8  test    ecx, ecx
0x1800250aa  jns     short loc_1800250C7
0x1800250ac  call    cs:__imp_RtlNtStatusToDosError
0x1800250b3  nop     dword ptr [rax+rax+00h]
0x1800250b8  mov     ebx, eax
0x1800250ba  test    eax, eax
0x1800250bc  jle     short loc_1800250C7
0x1800250be  movzx   ebx, ax
0x1800250c1  or      ebx, 80070000h
0x1800250c7  mov     rcx, [rsi]; Block
0x1800250ca  test    rcx, rcx
0x1800250cd  jz      short loc_1800250DB
0x1800250cf  call    cs:__imp_free
0x1800250d6  nop     dword ptr [rax+rax+00h]
0x1800250db  mov     rcx, rsi; Block
0x1800250de  call    cs:__imp_free
0x1800250e5  nop     dword ptr [rax+rax+00h]
0x1800250ea  cmp     [rbp+Block], 0
0x1800250ef  jz      short loc_180025101
0x1800250f1  mov     rcx, [rbp+Block]; Block
0x1800250f5  call    cs:__imp_free
0x1800250fc  nop     dword ptr [rax+rax+00h]
0x180025101  test    rdi, rdi
0x180025104  jz      short loc_180025115
0x180025106  mov     rcx, rdi; Block
0x180025109  call    cs:__imp_free
0x180025110  nop     dword ptr [rax+rax+00h]
0x180025115  mov     rcx, [rbp+hObject]; hObject
0x180025119  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002511d  jz      short loc_18002512B
0x18002511f  call    cs:__imp_CloseHandle
0x180025126  nop     dword ptr [rax+rax+00h]
0x18002512b  mov     eax, ebx
0x18002512d  lea     r11, [rsp+60h+var_s0]
0x180025132  mov     rbx, [r11+30h]
0x180025136  mov     rsi, [r11+38h]
0x18002513a  mov     rsp, r11
0x18002513d  pop     r15
0x18002513f  pop     rdi
0x180025140  pop     rbp
0x180025141  retn
```
