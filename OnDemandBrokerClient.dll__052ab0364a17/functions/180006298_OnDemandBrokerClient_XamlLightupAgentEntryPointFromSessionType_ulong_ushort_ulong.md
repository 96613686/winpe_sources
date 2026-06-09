# OnDemandBrokerClient::XamlLightupAgentEntryPointFromSessionType(ulong,ushort *,ulong)

- ea: `0x180006298`
- end: `0x180006303`
- name: `?XamlLightupAgentEntryPointFromSessionType@OnDemandBrokerClient@@AEAAJKPEAGK@Z`
- size: `107`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *this, int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800058f0`

## callees

- `0x180006298`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800062ed`
- `msvcrt!wcscpy_s` at `0x1800062ed`

## string_xrefs

- `0x1800062cc`: `AgHost.BackgroundAudioTask`
- `0x1800062d5`: `AgHost.BackgroundVoipTask`
- `0x1800062de`: `AgHost.BackgroundTask`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::XamlLightupAgentEntryPointFromSessionType(
        OnDemandBrokerClient *this,
        int a2,
        unsigned __int16 *a3)
{
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  const wchar_t *v11; // r8

  v4 = a2 - 705;
  if ( v4 && (v5 = v4 - 1) != 0 && (v6 = v5 - 1) != 0 )
  {
    v7 = v6 - 1;
    if ( v7 && (v8 = v7 - 1) != 0 && (v9 = v8 - 1) != 0 )
    {
      if ( v9 != 1 )
        return 2147549183LL;
      v11 = L"AgHost.BackgroundAudioTask";
    }
    else
    {
      v11 = L"AgHost.BackgroundVoipTask";
    }
  }
  else
  {
    v11 = L"AgHost.BackgroundTask";
  }
  return wcscpy_s(a3, 0x104u, v11) != 0 ? 0x8000FFFF : 0;
}

```

## disassembly

```asm
0x180006298  sub     rsp, 28h
0x18000629c  mov     rax, r8
0x18000629f  sub     edx, 2C1h
0x1800062a5  jz      short loc_1800062DE
0x1800062a7  sub     edx, 1
0x1800062aa  jz      short loc_1800062DE
0x1800062ac  sub     edx, 1
0x1800062af  jz      short loc_1800062DE
0x1800062b1  sub     edx, 1
0x1800062b4  jz      short loc_1800062D5
0x1800062b6  sub     edx, 1
0x1800062b9  jz      short loc_1800062D5
0x1800062bb  sub     edx, 1
0x1800062be  jz      short loc_1800062D5
0x1800062c0  cmp     edx, 1
0x1800062c3  jz      short loc_1800062CC
0x1800062c5  mov     eax, 8000FFFFh
0x1800062ca  jmp     short loc_1800062FE
0x1800062cc  lea     r8, aAghostBackgrou; "AgHost.BackgroundAudioTask"
0x1800062d3  jmp     short loc_1800062E5
0x1800062d5  lea     r8, aAghostBackgrou_0; "AgHost.BackgroundVoipTask"
0x1800062dc  jmp     short loc_1800062E5
0x1800062de  lea     r8, Source; "AgHost.BackgroundTask"
0x1800062e5  mov     edx, 104h; SizeInWords
0x1800062ea  mov     rcx, rax; Destination
0x1800062ed  call    cs:__imp_wcscpy_s
0x1800062f3  neg     eax
0x1800062f5  mov     eax, 8000FFFFh
0x1800062fa  sbb     ecx, ecx
0x1800062fc  and     eax, ecx
0x1800062fe  add     rsp, 28h
0x180006302  retn
```
