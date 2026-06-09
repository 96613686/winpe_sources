# CConfigServiceProvider2Impl::ConfigManagerNotification(ConfigManager2Notification,__int64)

- ea: `0x180014d10`
- end: `0x180014e70`
- name: `?ConfigManagerNotification@CConfigServiceProvider2Impl@@UEAAJW4ConfigManager2Notification@@_J@Z`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800032f0`

## callees

- `0x180014d10`
- `0x18003631c`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::ConfigManagerNotification(__int64 a1, int a2, __int64 a3)
{
  unsigned int v3; // ebx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  unsigned int v7; // edx
  int v8; // eax
  unsigned int v9; // edx
  int v10; // eax
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx

  v3 = 0;
  if ( a2 > 5 )
  {
    v11 = a2 - 6;
    if ( !v11 )
    {
      if ( *(_DWORD *)(a1 + 24) == 5 )
      {
        *(_DWORD *)(a1 + 24) = 6;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      if ( (*(_DWORD *)(a1 + 24) & 0xFFFFFFF9) == 0 && *(_DWORD *)(a1 + 24) != 6 )
      {
        *(_DWORD *)(a1 + 24) = 7;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      if ( *(_DWORD *)(a1 + 24) == 7 )
      {
        *(_DWORD *)(a1 + 24) = 8;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      if ( *(_DWORD *)(a1 + 24) == 1 || *(_DWORD *)(a1 + 24) == 10 )
      {
        *(_DWORD *)(a1 + 24) = 9;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    if ( v14 == 1 )
    {
      if ( *(_DWORD *)(a1 + 24) == 9 )
      {
        *(_DWORD *)(a1 + 24) = 10;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    goto LABEL_30;
  }
  if ( a2 == 5 )
  {
    if ( *(_DWORD *)(a1 + 24) == 2 )
    {
      *(_DWORD *)(a1 + 24) = 5;
      return v3;
    }
    return (unsigned int)-2147418113;
  }
  if ( !a2 )
  {
    if ( !*(_DWORD *)(a1 + 24) )
    {
      *(_DWORD *)(a1 + 24) = 0;
      return v3;
    }
    return (unsigned int)-2147418113;
  }
  v4 = a2 - 1;
  if ( !v4 )
  {
    v9 = *(_DWORD *)(a1 + 24);
    if ( v9 <= 8 )
    {
      v10 = 337;
      if ( _bittest(&v10, v9) )
      {
        *(_DWORD *)(a1 + 24) = 1;
        return v3;
      }
    }
    return (unsigned int)-2147418113;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    if ( *(_DWORD *)(a1 + 24) == 1 || *(_DWORD *)(a1 + 24) == 10 )
    {
      *(_DWORD *)(a1 + 24) = 2;
      return v3;
    }
    return (unsigned int)-2147418113;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v7 = *(_DWORD *)(a1 + 24);
    if ( v7 <= 8 )
    {
      v8 = 337;
      if ( _bittest(&v8, v7) )
      {
        *(_DWORD *)(a1 + 24) = 3;
        return v3;
      }
    }
    return (unsigned int)-2147418113;
  }
  if ( v6 != 1 )
  {
LABEL_30:
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return (unsigned int)-2147418113;
  }
  if ( *(_DWORD *)(a1 + 24) )
    return (unsigned int)-2147418113;
  *(_DWORD *)(a1 + 24) = 4;
  if ( a3 )
  {
    *(_QWORD *)(a1 + 16) = a3;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180014d10  push    rbx
0x180014d12  sub     rsp, 20h
0x180014d16  xor     r9d, r9d
0x180014d19  mov     ebx, r9d
0x180014d1c  lea     r10d, [r9+5]
0x180014d20  cmp     edx, r10d
0x180014d23  jg      loc_180014DEA
0x180014d29  jz      loc_180014DDE
0x180014d2f  test    edx, edx
0x180014d31  jz      loc_180014DD2
0x180014d37  sub     edx, 1
0x180014d3a  jz      short loc_180014DB7
0x180014d3c  sub     edx, 1
0x180014d3f  jz      short loc_180014DA2
0x180014d41  sub     edx, 1
0x180014d44  jz      short loc_180014D87
0x180014d46  cmp     edx, 1
0x180014d49  jnz     loc_180014E03
0x180014d4f  cmp     [rcx+18h], r9d
0x180014d53  jnz     loc_180014E08
0x180014d59  mov     dword ptr [rcx+18h], 4
0x180014d60  test    r8, r8
0x180014d63  jz      short loc_180014D7D
0x180014d65  mov     [rcx+10h], r8
0x180014d69  mov     rcx, r8
0x180014d6c  mov     rax, [r8]
0x180014d6f  mov     rax, [rax+8]
0x180014d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d78  jmp     loc_180014E0D
0x180014d7d  mov     ebx, 80070057h
0x180014d82  jmp     loc_180014E0D
0x180014d87  mov     edx, [rcx+18h]
0x180014d8a  cmp     edx, 8
0x180014d8d  ja      short loc_180014E08
0x180014d8f  mov     eax, 151h
0x180014d94  bt      eax, edx
0x180014d97  jnb     short loc_180014E08
0x180014d99  mov     dword ptr [rcx+18h], 3
0x180014da0  jmp     short loc_180014E0D
0x180014da2  cmp     dword ptr [rcx+18h], 1
0x180014da6  jz      short loc_180014DAE
0x180014da8  cmp     dword ptr [rcx+18h], 0Ah
0x180014dac  jnz     short loc_180014E08
0x180014dae  mov     dword ptr [rcx+18h], 2
0x180014db5  jmp     short loc_180014E0D
0x180014db7  mov     edx, [rcx+18h]
0x180014dba  cmp     edx, 8
0x180014dbd  ja      short loc_180014E08
0x180014dbf  mov     eax, 151h
0x180014dc4  bt      eax, edx
0x180014dc7  jnb     short loc_180014E08
0x180014dc9  mov     dword ptr [rcx+18h], 1
0x180014dd0  jmp     short loc_180014E0D
0x180014dd2  cmp     [rcx+18h], r9d
0x180014dd6  jnz     short loc_180014E08
0x180014dd8  mov     [rcx+18h], r9d
0x180014ddc  jmp     short loc_180014E0D
0x180014dde  cmp     dword ptr [rcx+18h], 2
0x180014de2  jnz     short loc_180014E08
0x180014de4  mov     [rcx+18h], r10d
0x180014de8  jmp     short loc_180014E0D
0x180014dea  sub     edx, 6
0x180014ded  jz      short loc_180014E61
0x180014def  sub     edx, 1
0x180014df2  jz      short loc_180014E49
0x180014df4  sub     edx, 1
0x180014df7  jz      short loc_180014E3A
0x180014df9  sub     edx, 1
0x180014dfc  jz      short loc_180014E25
0x180014dfe  cmp     edx, 1
0x180014e01  jz      short loc_180014E16
0x180014e03  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014e08  mov     ebx, 8000FFFFh
0x180014e0d  mov     eax, ebx
0x180014e0f  add     rsp, 20h
0x180014e13  pop     rbx
0x180014e14  retn
0x180014e16  cmp     dword ptr [rcx+18h], 9
0x180014e1a  jnz     short loc_180014E08
0x180014e1c  mov     dword ptr [rcx+18h], 0Ah
0x180014e23  jmp     short loc_180014E0D
0x180014e25  cmp     dword ptr [rcx+18h], 1
0x180014e29  jz      short loc_180014E31
0x180014e2b  cmp     dword ptr [rcx+18h], 0Ah
0x180014e2f  jnz     short loc_180014E08
0x180014e31  mov     dword ptr [rcx+18h], 9
0x180014e38  jmp     short loc_180014E0D
0x180014e3a  cmp     dword ptr [rcx+18h], 7
0x180014e3e  jnz     short loc_180014E08
0x180014e40  mov     dword ptr [rcx+18h], 8
0x180014e47  jmp     short loc_180014E0D
0x180014e49  test    dword ptr [rcx+18h], 0FFFFFFF9h
0x180014e50  jnz     short loc_180014E08
0x180014e52  cmp     dword ptr [rcx+18h], 6
0x180014e56  jz      short loc_180014E08
0x180014e58  mov     dword ptr [rcx+18h], 7
0x180014e5f  jmp     short loc_180014E0D
0x180014e61  cmp     [rcx+18h], r10d
0x180014e65  jnz     short loc_180014E08
0x180014e67  mov     dword ptr [rcx+18h], 6
0x180014e6e  jmp     short loc_180014E0D
```
