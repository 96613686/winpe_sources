# CommonUtil::HrChangeServiceConfig2W(SC_HANDLE__ *,ulong,void *)

- ea: `0x140015c98`
- end: `0x140015cb6`
- name: `?HrChangeServiceConfig2W@CommonUtil@@YAJPEAUSC_HANDLE__@@KPEAX@Z`
- size: `30`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, struct SC_HANDLE__ *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140089c78`

## callees

- `0x140015c98`
- `0x140017738`

## import_xrefs

- `ADVAPI32!ChangeServiceConfig2W` at `0x140015c9c`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140015c9c`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrChangeServiceConfig2W(CommonUtil *this, struct SC_HANDLE__ *a2, void *a3, void *a4)
{
  BOOL v4; // eax
  unsigned int v5; // ecx

  v4 = ChangeServiceConfig2W((SC_HANDLE)this, (DWORD)a2, a3);
  v5 = 0;
  if ( !v4 )
    return (unsigned int)HrGetLastFailure(0);
  return v5;
}

```

## disassembly

```asm
0x140015c98  sub     rsp, 28h
0x140015c9c  call    cs:__imp_ChangeServiceConfig2W
0x140015ca2  xor     ecx, ecx
0x140015ca4  test    eax, eax
0x140015ca6  jnz     short loc_140015CAF
0x140015ca8  call    HrGetLastFailure
0x140015cad  mov     ecx, eax
0x140015caf  mov     eax, ecx
0x140015cb1  add     rsp, 28h
0x140015cb5  retn
```
