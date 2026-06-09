# CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)

- ea: `0x18000e978`
- end: `0x18000e9b2`
- name: `??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z`
- size: `58`
- prototype: `CAutoSetThreadActivityId *__fastcall(LPGUID ActivityId, const struct _GUID *)`
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f790`
- `0x18000f9e0`
- `0x18000fb90`
- `0x18000fdc0`
- `0x18000ffb0`
- `0x180011630`
- `0x180011a60`
- `0x180011c30`
- `0x180013fdc`
- `0x18001b8f0`
- `0x18001bb40`
- `0x18001bdd0`
- `0x180025f90`
- `0x180026190`
- `0x1800263c0`
- `0x1800265f0`
- `0x180026740`
- `0x180026920`
- `0x180026b00`
- `0x180026ee0`
- `0x18002d2f0`
- `0x18002d360`
- `0x1800303a8`

## callees

- `0x18000e978`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000e99c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000e99c`

## pseudocode

```c
CAutoSetThreadActivityId *__fastcall CAutoSetThreadActivityId::CAutoSetThreadActivityId(
        LPGUID ActivityId,
        const struct _GUID *a2)
{
  ULONG v3; // ecx

  if ( a2 )
  {
    *ActivityId = *a2;
    v3 = 4;
  }
  else
  {
    v3 = 1;
  }
  EventActivityIdControl(v3, ActivityId);
  return (CAutoSetThreadActivityId *)ActivityId;
}

```

## disassembly

```asm
0x18000e978  push    rbx
0x18000e97a  sub     rsp, 20h
0x18000e97e  mov     rbx, rcx
0x18000e981  test    rdx, rdx
0x18000e984  jz      short loc_18000E994
0x18000e986  movups  xmm0, xmmword ptr [rdx]
0x18000e989  movdqu  xmmword ptr [rcx], xmm0
0x18000e98d  mov     ecx, 4
0x18000e992  jmp     short loc_18000E999
0x18000e994  mov     ecx, 1; ControlCode
0x18000e999  mov     rdx, rbx; ActivityId
0x18000e99c  call    cs:__imp_EventActivityIdControl
0x18000e9a3  nop     dword ptr [rax+rax+00h]
0x18000e9a8  mov     rax, rbx
0x18000e9ab  add     rsp, 20h
0x18000e9af  pop     rbx
0x18000e9b0  retn
```
