# CreateReadWriteLock

- ea: `0x180007df0`
- end: `0x180007f69`
- name: `CreateReadWriteLock`
- size: `377`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180007df0`
- `0x180008ff0`
- `0x180009130`
- `0x18000b6f4`
- `0x18000b734`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eff`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007f0b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007f0b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007e8d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007e8d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007e2e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007e2e`

## pseudocode

```c
__int64 __fastcall CreateReadWriteLock(__int64 a1)
{
  DWORD LastError; // esi
  HANDLE EventW; // rax
  PVOID *v4; // rcx

  LastError = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ae89183a349339de188038c4f0a19280_Traceguids);
  *(_DWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 4) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  *(_DWORD *)(a1 + 4) = 1;
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 56) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    *(_DWORD *)(a1 + 4) = 0;
    if ( LastError )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return LastError;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_8;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ae89183a349339de188038c4f0a19280_Traceguids, LastError);
      goto LABEL_16;
    }
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return LastError;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ae89183a349339de188038c4f0a19280_Traceguids, a1);
LABEL_16:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_8:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_L(v4[2], 14, WPP_ae89183a349339de188038c4f0a19280_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180007df0  push    rbx
0x180007df2  push    rsi
0x180007df3  push    rdi
0x180007df4  push    r14
0x180007df6  push    r15
0x180007df8  sub     rsp, 20h
0x180007dfc  mov     rbx, rcx
0x180007dff  xor     r15d, r15d
0x180007e02  mov     esi, r15d
0x180007e05  lea     rdi, WPP_GLOBAL_Control
0x180007e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e13  cmp     rcx, rdi
0x180007e16  jz      short loc_180007E22
0x180007e18  test    byte ptr [rcx+1Ch], 8
0x180007e1c  jnz     loc_180007EE5
0x180007e22  mov     [rbx+30h], r15d
0x180007e26  mov     [rbx+4], r15d
0x180007e2a  lea     rcx, [rbx+8]; lpCriticalSection
0x180007e2e  call    cs:__imp_InitializeCriticalSection
0x180007e34  jmp     short loc_180007E7C
0x180007e36  mov     esi, 0Eh
0x180007e3b  lea     rax, WPP_GLOBAL_Control
0x180007e42  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e49  cmp     rcx, rax
0x180007e4c  jz      short loc_180007E73
0x180007e4e  test    byte ptr [rcx+1Ch], 4
0x180007e52  jz      short loc_180007E73
0x180007e54  mov     edx, 0Bh
0x180007e59  mov     r9d, esi
0x180007e5c  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x180007e63  mov     rcx, [rcx+10h]
0x180007e67  call    WPP_SF_d
0x180007e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e73  lea     rdi, WPP_GLOBAL_Control
0x180007e7a  jmp     short loc_180007EC0
0x180007e7c  mov     dword ptr [rbx+4], 1
0x180007e83  xor     r9d, r9d; lpName
0x180007e86  xor     r8d, r8d; bInitialState
0x180007e89  xor     edx, edx; bManualReset
0x180007e8b  xor     ecx, ecx; lpEventAttributes
0x180007e8d  call    cs:__imp_CreateEventW
0x180007e93  mov     [rbx+38h], rax
0x180007e97  test    rax, rax
0x180007e9a  jz      short loc_180007EFF
0x180007e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ea3  cmp     rcx, rdi
0x180007ea6  jnz     short loc_180007EB6
0x180007ea8  mov     eax, esi
0x180007eaa  add     rsp, 20h
0x180007eae  pop     r15
0x180007eb0  pop     r14
0x180007eb2  pop     rdi
0x180007eb3  pop     rsi
0x180007eb4  pop     rbx
0x180007eb5  retn
0x180007eb6  test    byte ptr [rcx+1Ch], 2
0x180007eba  jnz     loc_180007F45
0x180007ec0  cmp     rcx, rdi
0x180007ec3  jz      short loc_180007EA8
0x180007ec5  test    byte ptr [rcx+1Ch], 8
0x180007ec9  jz      short loc_180007EA8
0x180007ecb  mov     edx, 0Eh
0x180007ed0  mov     r9d, esi
0x180007ed3  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x180007eda  mov     rcx, [rcx+10h]
0x180007ede  call    WPP_SF_L
0x180007ee3  jmp     short loc_180007EA8
0x180007ee5  mov     edx, 0Ah
0x180007eea  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x180007ef1  mov     rcx, [rcx+10h]
0x180007ef5  call    WPP_SF_
0x180007efa  jmp     loc_180007E22
0x180007eff  call    cs:__imp_GetLastError
0x180007f05  mov     esi, eax
0x180007f07  lea     rcx, [rbx+8]; lpCriticalSection
0x180007f0b  call    cs:__imp_DeleteCriticalSection
0x180007f11  mov     [rbx+4], r15d
0x180007f15  test    esi, esi
0x180007f17  jz      short loc_180007E9C
0x180007f19  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f20  cmp     rcx, rdi
0x180007f23  jz      short loc_180007EA8
0x180007f25  test    byte ptr [rcx+1Ch], 4
0x180007f29  jz      short loc_180007EC0
0x180007f2b  mov     edx, 0Ch
0x180007f30  mov     r9d, esi
0x180007f33  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x180007f3a  mov     rcx, [rcx+10h]
0x180007f3e  call    WPP_SF_d
0x180007f43  jmp     short loc_180007F5D
0x180007f45  mov     edx, 0Dh
0x180007f4a  mov     r9, rbx
0x180007f4d  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x180007f54  mov     rcx, [rcx+10h]
0x180007f58  call    WPP_SF_q
0x180007f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f64  jmp     loc_180007EC0
```
