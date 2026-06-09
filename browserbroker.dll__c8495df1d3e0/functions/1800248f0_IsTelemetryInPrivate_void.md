# IsTelemetryInPrivate(void)

- ea: `0x1800248f0`
- end: `0x1800249b2`
- name: `?IsTelemetryInPrivate@@YA_NXZ`
- size: `194`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800010c4`

## callees

- `0x1800248f0`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180024987`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180024987`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18002497d`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18002497d`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180024971`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180024971`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18002491b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18002492f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18002491b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18002492f`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18002490e`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18002490e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024942`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024942`
- `edgeIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180024957`
- `edgeIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180024957`

## pseudocode

```c
char IsTelemetryInPrivate(void)
{
  int DWORD; // edi
  DWORD CurrentThreadId; // eax
  char v2; // bl
  bool v3; // al
  struct _IsoComponent *v5; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18003F2FC != 2 )
    return dword_18003F2FC == 1;
  DWORD = IEConfiguration_GetDWORD(268435501);
  if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
  {
    v2 = 1;
    if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
    {
      v3 = LCIEIsCurrentProcessInPrivate();
      v2 = v3;
      if ( DWORD != 3 )
        dword_18003F2FC = v3;
    }
  }
  else
  {
    if ( (unsigned __int8)IEConfiguration_GetBool(268435512) )
      return LCIEIsCurrentProcessUsingInPrivateComponents();
    v5 = 0;
    CurrentThreadId = GetCurrentThreadId();
    if ( (int)LCIEGetTypedComponentFromThread(0x200u, CurrentThreadId, 0, &v5) < 0 )
      return LCIEIsCurrentProcessUsingInPrivateComponents();
    else
      return (*((_DWORD *)v5 + 21) & 0x40) != 0;
  }
  return v2;
}

```

## disassembly

```asm
0x1800248f0  mov     [rsp+arg_8], rbx
0x1800248f5  push    rdi
0x1800248f6  sub     rsp, 20h
0x1800248fa  mov     eax, cs:dword_18003F2FC
0x180024900  cmp     eax, 2
0x180024903  jnz     loc_18002499F
0x180024909  mov     ecx, 1000002Dh
0x18002490e  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180024914  mov     ecx, 20000002h
0x180024919  mov     edi, eax
0x18002491b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180024921  test    al, al
0x180024923  jnz     short loc_18002497B
0x180024925  cmp     edi, 2
0x180024928  jnz     short loc_18002497B
0x18002492a  mov     ecx, 10000038h
0x18002492f  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180024935  test    al, al
0x180024937  jnz     short loc_180024971
0x180024939  mov     [rsp+28h+arg_0], 0
0x180024942  call    cs:__imp_GetCurrentThreadId
0x180024948  lea     r9, [rsp+28h+arg_0]
0x18002494d  xor     r8d, r8d
0x180024950  mov     edx, eax
0x180024952  mov     ecx, 200h
0x180024957  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x18002495d  test    eax, eax
0x18002495f  js      short loc_180024971
0x180024961  mov     rax, [rsp+28h+arg_0]
0x180024966  mov     ebx, [rax+54h]
0x180024969  shr     ebx, 6
0x18002496c  and     bl, 1
0x18002496f  jmp     short loc_1800249A5
0x180024971  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180024977  mov     bl, al
0x180024979  jmp     short loc_1800249A5
0x18002497b  mov     bl, 1
0x18002497d  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x180024983  test    al, al
0x180024985  jz      short loc_1800249A5
0x180024987  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x18002498d  mov     bl, al
0x18002498f  cmp     edi, 3
0x180024992  jz      short loc_1800249A5
0x180024994  movzx   eax, al
0x180024997  mov     cs:dword_18003F2FC, eax
0x18002499d  jmp     short loc_1800249A5
0x18002499f  cmp     eax, 1
0x1800249a2  setz    bl
0x1800249a5  mov     al, bl
0x1800249a7  mov     rbx, [rsp+28h+arg_8]
0x1800249ac  add     rsp, 20h
0x1800249b0  pop     rdi
0x1800249b1  retn
```
