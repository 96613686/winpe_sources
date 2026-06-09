# CConfigServiceProvider2Impl::ConfigManagerNotification(ConfigManager2Notification,__int64)

- ea: `0x180014250`
- end: `0x1800143af`
- name: `?ConfigManagerNotification@CConfigServiceProvider2Impl@@UEAAJW4ConfigManager2Notification@@_J@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003290`

## callees

- `0x180014250`
- `0x180034cb8`
- `0x180037010`

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
0x180014250  push    rbx
0x180014252  sub     rsp, 20h
0x180014256  xor     r9d, r9d
0x180014259  mov     ebx, r9d
0x18001425c  lea     r10d, [r9+5]
0x180014260  cmp     edx, r10d
0x180014263  jg      loc_18001432A
0x180014269  jz      loc_18001431E
0x18001426f  test    edx, edx
0x180014271  jz      loc_180014312
0x180014277  sub     edx, 1
0x18001427a  jz      short loc_1800142F7
0x18001427c  sub     edx, 1
0x18001427f  jz      short loc_1800142E2
0x180014281  sub     edx, 1
0x180014284  jz      short loc_1800142C7
0x180014286  cmp     edx, 1
0x180014289  jnz     loc_180014343
0x18001428f  cmp     [rcx+18h], r9d
0x180014293  jnz     loc_180014348
0x180014299  mov     dword ptr [rcx+18h], 4
0x1800142a0  test    r8, r8
0x1800142a3  jz      short loc_1800142BD
0x1800142a5  mov     [rcx+10h], r8
0x1800142a9  mov     rcx, r8
0x1800142ac  mov     rax, [r8]
0x1800142af  mov     rax, [rax+8]
0x1800142b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142b8  jmp     loc_18001434D
0x1800142bd  mov     ebx, 80070057h
0x1800142c2  jmp     loc_18001434D
0x1800142c7  mov     edx, [rcx+18h]
0x1800142ca  cmp     edx, 8
0x1800142cd  ja      short loc_180014348
0x1800142cf  mov     eax, 151h
0x1800142d4  bt      eax, edx
0x1800142d7  jnb     short loc_180014348
0x1800142d9  mov     dword ptr [rcx+18h], 3
0x1800142e0  jmp     short loc_18001434D
0x1800142e2  cmp     dword ptr [rcx+18h], 1
0x1800142e6  jz      short loc_1800142EE
0x1800142e8  cmp     dword ptr [rcx+18h], 0Ah
0x1800142ec  jnz     short loc_180014348
0x1800142ee  mov     dword ptr [rcx+18h], 2
0x1800142f5  jmp     short loc_18001434D
0x1800142f7  mov     edx, [rcx+18h]
0x1800142fa  cmp     edx, 8
0x1800142fd  ja      short loc_180014348
0x1800142ff  mov     eax, 151h
0x180014304  bt      eax, edx
0x180014307  jnb     short loc_180014348
0x180014309  mov     dword ptr [rcx+18h], 1
0x180014310  jmp     short loc_18001434D
0x180014312  cmp     [rcx+18h], r9d
0x180014316  jnz     short loc_180014348
0x180014318  mov     [rcx+18h], r9d
0x18001431c  jmp     short loc_18001434D
0x18001431e  cmp     dword ptr [rcx+18h], 2
0x180014322  jnz     short loc_180014348
0x180014324  mov     [rcx+18h], r10d
0x180014328  jmp     short loc_18001434D
0x18001432a  sub     edx, 6
0x18001432d  jz      short loc_1800143A0
0x18001432f  sub     edx, 1
0x180014332  jz      short loc_180014388
0x180014334  sub     edx, 1
0x180014337  jz      short loc_180014379
0x180014339  sub     edx, 1
0x18001433c  jz      short loc_180014364
0x18001433e  cmp     edx, 1
0x180014341  jz      short loc_180014355
0x180014343  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014348  mov     ebx, 8000FFFFh
0x18001434d  mov     eax, ebx
0x18001434f  add     rsp, 20h
0x180014353  pop     rbx
0x180014354  retn
0x180014355  cmp     dword ptr [rcx+18h], 9
0x180014359  jnz     short loc_180014348
0x18001435b  mov     dword ptr [rcx+18h], 0Ah
0x180014362  jmp     short loc_18001434D
0x180014364  cmp     dword ptr [rcx+18h], 1
0x180014368  jz      short loc_180014370
0x18001436a  cmp     dword ptr [rcx+18h], 0Ah
0x18001436e  jnz     short loc_180014348
0x180014370  mov     dword ptr [rcx+18h], 9
0x180014377  jmp     short loc_18001434D
0x180014379  cmp     dword ptr [rcx+18h], 7
0x18001437d  jnz     short loc_180014348
0x18001437f  mov     dword ptr [rcx+18h], 8
0x180014386  jmp     short loc_18001434D
0x180014388  test    dword ptr [rcx+18h], 0FFFFFFF9h
0x18001438f  jnz     short loc_180014348
0x180014391  cmp     dword ptr [rcx+18h], 6
0x180014395  jz      short loc_180014348
0x180014397  mov     dword ptr [rcx+18h], 7
0x18001439e  jmp     short loc_18001434D
0x1800143a0  cmp     [rcx+18h], r10d
0x1800143a4  jnz     short loc_180014348
0x1800143a6  mov     dword ptr [rcx+18h], 6
0x1800143ad  jmp     short loc_18001434D
```
