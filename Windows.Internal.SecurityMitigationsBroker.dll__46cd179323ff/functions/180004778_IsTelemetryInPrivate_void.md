# IsTelemetryInPrivate(void)

- ea: `0x180004778`
- end: `0x180004821`
- name: `?IsTelemetryInPrivate@@YA_NXZ`
- size: `169`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000113c`

## callees

- `0x180004778`
- `0x180007010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1800047f7`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1800047f7`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x1800047ed`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x1800047ed`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800047e3`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800047e3`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800047a4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800047b8`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800047a4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800047b8`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180004797`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180004797`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x1800047c2`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x1800047c2`

## pseudocode

```c
bool IsTelemetryInPrivate(void)
{
  int DWORD; // ebx
  struct IEdgeBrowsingEnvironment *EdgeBrowsingEnvironment; // rax
  BOOL v2; // ecx
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 1;
  if ( dword_18000C150 != 2 )
  {
    LOBYTE(v2) = dword_18000C150 == 1;
    return v2;
  }
  DWORD = IEConfiguration_GetDWORD(268435501);
  if ( !(unsigned __int8)IEConfiguration_GetBool(536870914) && DWORD == 2 )
  {
    if ( (unsigned __int8)IEConfiguration_GetBool(268435512)
      || (EdgeBrowsingEnvironment = GetEdgeBrowsingEnvironment(),
          (*(int (__fastcall **)(struct IEdgeBrowsingEnvironment *, char *))(*(_QWORD *)EdgeBrowsingEnvironment + 120LL))(
            EdgeBrowsingEnvironment,
            &v4) < 0) )
    {
      LOBYTE(v2) = LCIEIsCurrentProcessUsingInPrivateComponents();
      return v2;
    }
LABEL_10:
    LOBYTE(v2) = v4;
    return v2;
  }
  if ( !LCIEIsCurrentProcessInPrivateOverrideSet() )
    goto LABEL_10;
  v2 = LCIEIsCurrentProcessInPrivate();
  if ( DWORD != 3 )
    dword_18000C150 = v2;
  return v2;
}

```

## disassembly

```asm
0x180004778  push    rbx
0x18000477a  sub     rsp, 20h
0x18000477e  mov     eax, cs:dword_18000C150
0x180004784  mov     [rsp+28h+arg_0], 1
0x180004789  cmp     eax, 2
0x18000478c  jnz     loc_180004813
0x180004792  mov     ecx, 1000002Dh
0x180004797  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18000479d  mov     ecx, 20000002h
0x1800047a2  mov     ebx, eax
0x1800047a4  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800047aa  test    al, al
0x1800047ac  jnz     short loc_1800047ED
0x1800047ae  cmp     ebx, 2
0x1800047b1  jnz     short loc_1800047ED
0x1800047b3  mov     ecx, 10000038h
0x1800047b8  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800047be  test    al, al
0x1800047c0  jnz     short loc_1800047E3
0x1800047c2  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x1800047c8  mov     r8, rax
0x1800047cb  lea     rdx, [rsp+28h+arg_0]
0x1800047d0  mov     rcx, [rax]
0x1800047d3  mov     rax, [rcx+78h]
0x1800047d7  mov     rcx, r8
0x1800047da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047df  test    eax, eax
0x1800047e1  jns     short loc_18000480D
0x1800047e3  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x1800047e9  mov     cl, al
0x1800047eb  jmp     short loc_180004819
0x1800047ed  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x1800047f3  test    al, al
0x1800047f5  jz      short loc_18000480D
0x1800047f7  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1800047fd  movzx   ecx, al
0x180004800  cmp     ebx, 3
0x180004803  jz      short loc_180004819
0x180004805  mov     cs:dword_18000C150, ecx
0x18000480b  jmp     short loc_180004819
0x18000480d  mov     cl, [rsp+28h+arg_0]
0x180004811  jmp     short loc_180004819
0x180004813  cmp     eax, 1
0x180004816  setz    cl
0x180004819  mov     al, cl
0x18000481b  add     rsp, 20h
0x18000481f  pop     rbx
0x180004820  retn
```
