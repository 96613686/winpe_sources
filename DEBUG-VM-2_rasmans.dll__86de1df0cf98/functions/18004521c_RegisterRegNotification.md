# RegisterRegNotification

- ea: `0x18004521c`
- end: `0x1800454ab`
- name: `RegisterRegNotification`
- size: `655`
- prototype: `__int64 __fastcall(PHKEY phkResult, PHKEY)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800408f0`
- `0x180044198`

## callees

- `0x180005e34`
- `0x18000bf70`
- `0x18004521c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800452c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800452c3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800452a8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800452b9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800452a8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800452b9`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800453c2`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004543a`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800453c2`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004543a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004531c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180045371`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004531c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180045371`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004527b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045290`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004527b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045290`

## string_xrefs

- `0x18004530e`: `System\CurrentControlSet\Services\LanmanServer\Linkage`
- `0x180045363`: `System\CurrentControlSet\Services\LanmanWorkstation\Linkage`

## pseudocode

```c
__int64 __fastcall RegisterRegNotification(PHKEY phkResult, PHKEY a2, int a3, __int64 a4)
{
  DWORD LastError; // eax
  DWORD v8; // ebx
  struct _LIST_ENTRY *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // r9

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    LOBYTE(a4) = a3 != 0;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 689, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, a4);
  }
  if ( *phkResult )
  {
    RegCloseKey(*phkResult);
    *phkResult = 0;
  }
  if ( *a2 )
  {
    RegCloseKey(*a2);
    *phkResult = 0;
  }
  if ( a3 && (!ResetEvent(hEvent) || !ResetEvent(qword_18010FED0)) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v8;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_44;
      v10 = 690;
LABEL_41:
      v12 = LastError;
LABEL_42:
      WPP_SF_d(v9[1].Flink, v10, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v12);
    }
LABEL_43:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_44;
  }
  LastError = RegOpenKeyExA(
                HKEY_LOCAL_MACHINE,
                "System\\CurrentControlSet\\Services\\LanmanServer\\Linkage",
                0,
                0x10u,
                phkResult);
  v8 = LastError;
  if ( LastError )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return v8;
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_44;
    v10 = 691;
    goto LABEL_41;
  }
  LastError = RegOpenKeyExA(
                HKEY_LOCAL_MACHINE,
                "System\\CurrentControlSet\\Services\\LanmanWorkstation\\Linkage",
                0,
                0x10u,
                a2);
  v8 = LastError;
  if ( LastError )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return v8;
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_44;
    v10 = 692;
    goto LABEL_41;
  }
  v11 = RegNotifyChangeKeyValue(*phkResult, 0, 4u, hEvent, 1);
  v8 = v11;
  if ( !v11 )
  {
    LastError = RegNotifyChangeKeyValue(*a2, 0, 4u, qword_18010FED0, 1);
    v8 = LastError;
    if ( LastError )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v8;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_44;
      v10 = 695;
      goto LABEL_41;
    }
    goto LABEL_43;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 693, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v11);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(v9[1].Blink) & 0x2000) == 0 || BYTE1(v9[1].Blink) < 2u )
      {
LABEL_44:
        if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v9[1].Blink) & 0x2000) != 0
          && BYTE1(v9[1].Blink) >= 6u )
        {
          WPP_SF_d(v9[1].Flink, 696, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v8);
        }
        return v8;
      }
      v10 = 694;
      v12 = v8;
      goto LABEL_42;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18004521c  push    rbx
0x18004521e  push    rbp
0x18004521f  push    rsi
0x180045220  push    rdi
0x180045221  push    r14
0x180045223  push    r15
0x180045225  sub     rsp, 38h
0x180045229  mov     ebx, r8d
0x18004522c  mov     rsi, rdx
0x18004522f  mov     rdi, rcx
0x180045232  mov     rcx, cs:WPP_GLOBAL_Control
0x180045239  lea     r14, WPP_GLOBAL_Control
0x180045240  lea     r15, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180045247  mov     ebp, 2000h
0x18004524c  cmp     rcx, r14
0x18004524f  jz      short loc_180045273
0x180045251  test    [rcx+1Ch], ebp
0x180045254  jz      short loc_180045273
0x180045256  cmp     byte ptr [rcx+19h], 6
0x18004525a  jb      short loc_180045273
0x18004525c  mov     rcx, [rcx+10h]
0x180045260  test    ebx, ebx
0x180045262  mov     edx, 2B1h
0x180045267  mov     r8, r15
0x18004526a  setnz   r9b
0x18004526e  call    WPP_SF_c
0x180045273  mov     rcx, [rdi]; hKey
0x180045276  test    rcx, rcx
0x180045279  jz      short loc_180045288
0x18004527b  call    cs:__imp_RegCloseKey
0x180045281  mov     qword ptr [rdi], 0
0x180045288  mov     rcx, [rsi]; hKey
0x18004528b  test    rcx, rcx
0x18004528e  jz      short loc_18004529D
0x180045290  call    cs:__imp_RegCloseKey
0x180045296  mov     qword ptr [rdi], 0
0x18004529d  test    ebx, ebx
0x18004529f  jz      short loc_180045300
0x1800452a1  mov     rcx, cs:hEvent; hEvent
0x1800452a8  call    cs:__imp_ResetEvent
0x1800452ae  test    eax, eax
0x1800452b0  jz      short loc_1800452C3
0x1800452b2  mov     rcx, cs:qword_18010FED0; hEvent
0x1800452b9  call    cs:__imp_ResetEvent
0x1800452bf  test    eax, eax
0x1800452c1  jnz     short loc_180045300
0x1800452c3  call    cs:__imp_GetLastError
0x1800452c9  mov     ebx, eax
0x1800452cb  test    eax, eax
0x1800452cd  jz      loc_180045471
0x1800452d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800452da  cmp     rcx, r14
0x1800452dd  jz      loc_18004549C
0x1800452e3  test    [rcx+1Ch], ebp
0x1800452e6  jz      loc_180045478
0x1800452ec  cmp     byte ptr [rcx+19h], 2
0x1800452f0  jb      loc_180045478
0x1800452f6  mov     edx, 2B2h
0x1800452fb  jmp     loc_180045462
0x180045300  mov     r9d, 10h; samDesired
0x180045306  mov     [rsp+68h+phkResult], rdi; phkResult
0x18004530b  xor     r8d, r8d; ulOptions
0x18004530e  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\La"...
0x180045315  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004531c  call    cs:__imp_RegOpenKeyExA
0x180045322  mov     ebx, eax
0x180045324  test    eax, eax
0x180045326  jz      short loc_180045355
0x180045328  mov     rcx, cs:WPP_GLOBAL_Control
0x18004532f  cmp     rcx, r14
0x180045332  jz      loc_18004549C
0x180045338  test    [rcx+1Ch], ebp
0x18004533b  jz      loc_180045478
0x180045341  cmp     byte ptr [rcx+19h], 2
0x180045345  jb      loc_180045478
0x18004534b  mov     edx, 2B3h
0x180045350  jmp     loc_180045462
0x180045355  mov     r9d, 10h; samDesired
0x18004535b  mov     [rsp+68h+phkResult], rsi; phkResult
0x180045360  xor     r8d, r8d; ulOptions
0x180045363  lea     rdx, aSystemCurrentc_18; "System\\CurrentControlSet\\Services\\La"...
0x18004536a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180045371  call    cs:__imp_RegOpenKeyExA
0x180045377  mov     ebx, eax
0x180045379  test    eax, eax
0x18004537b  jz      short loc_1800453AA
0x18004537d  mov     rcx, cs:WPP_GLOBAL_Control
0x180045384  cmp     rcx, r14
0x180045387  jz      loc_18004549C
0x18004538d  test    [rcx+1Ch], ebp
0x180045390  jz      loc_180045478
0x180045396  cmp     byte ptr [rcx+19h], 2
0x18004539a  jb      loc_180045478
0x1800453a0  mov     edx, 2B4h
0x1800453a5  jmp     loc_180045462
0x1800453aa  mov     r9, cs:hEvent; hEvent
0x1800453b1  xor     edx, edx; bWatchSubtree
0x1800453b3  mov     rcx, [rdi]; hKey
0x1800453b6  mov     dword ptr [rsp+68h+phkResult], 1; fAsynchronous
0x1800453be  lea     r8d, [rdx+4]; dwNotifyFilter
0x1800453c2  call    cs:__imp_RegNotifyChangeKeyValue
0x1800453c8  mov     ebx, eax
0x1800453ca  test    eax, eax
0x1800453cc  jz      short loc_180045422
0x1800453ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800453d5  cmp     rcx, r14
0x1800453d8  jz      loc_18004549C
0x1800453de  test    [rcx+1Ch], ebp
0x1800453e1  jz      short loc_180045404
0x1800453e3  cmp     byte ptr [rcx+19h], 2
0x1800453e7  jb      short loc_180045404
0x1800453e9  mov     rcx, [rcx+10h]
0x1800453ed  mov     edx, 2B5h
0x1800453f2  mov     r9d, eax
0x1800453f5  mov     r8, r15
0x1800453f8  call    WPP_SF_d
0x1800453fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180045404  cmp     rcx, r14
0x180045407  jz      loc_18004549C
0x18004540d  test    [rcx+1Ch], ebp
0x180045410  jz      short loc_180045478
0x180045412  cmp     byte ptr [rcx+19h], 2
0x180045416  jb      short loc_180045478
0x180045418  mov     edx, 2B6h
0x18004541d  mov     r9d, ebx
0x180045420  jmp     short loc_180045465
0x180045422  mov     r9, cs:qword_18010FED0; hEvent
0x180045429  xor     edx, edx; bWatchSubtree
0x18004542b  mov     rcx, [rsi]; hKey
0x18004542e  mov     dword ptr [rsp+68h+phkResult], 1; fAsynchronous
0x180045436  lea     r8d, [rdx+4]; dwNotifyFilter
0x18004543a  call    cs:__imp_RegNotifyChangeKeyValue
0x180045440  mov     ebx, eax
0x180045442  test    eax, eax
0x180045444  jz      short loc_180045471
0x180045446  mov     rcx, cs:WPP_GLOBAL_Control
0x18004544d  cmp     rcx, r14
0x180045450  jz      short loc_18004549C
0x180045452  test    [rcx+1Ch], ebp
0x180045455  jz      short loc_180045478
0x180045457  cmp     byte ptr [rcx+19h], 2
0x18004545b  jb      short loc_180045478
0x18004545d  mov     edx, 2B7h
0x180045462  mov     r9d, eax
0x180045465  mov     rcx, [rcx+10h]
0x180045469  mov     r8, r15
0x18004546c  call    WPP_SF_d
0x180045471  mov     rcx, cs:WPP_GLOBAL_Control
0x180045478  cmp     rcx, r14
0x18004547b  jz      short loc_18004549C
0x18004547d  test    [rcx+1Ch], ebp
0x180045480  jz      short loc_18004549C
0x180045482  cmp     byte ptr [rcx+19h], 6
0x180045486  jb      short loc_18004549C
0x180045488  mov     rcx, [rcx+10h]
0x18004548c  mov     edx, 2B8h
0x180045491  mov     r9d, ebx
0x180045494  mov     r8, r15
0x180045497  call    WPP_SF_d
0x18004549c  mov     eax, ebx
0x18004549e  add     rsp, 38h
0x1800454a2  pop     r15
0x1800454a4  pop     r14
0x1800454a6  pop     rdi
0x1800454a7  pop     rsi
0x1800454a8  pop     rbp
0x1800454a9  pop     rbx
0x1800454aa  retn
```
