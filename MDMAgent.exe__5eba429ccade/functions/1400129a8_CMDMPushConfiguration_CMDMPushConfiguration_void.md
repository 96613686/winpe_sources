# CMDMPushConfiguration::~CMDMPushConfiguration(void)

- ea: `0x1400129a8`
- end: `0x1400129cd`
- name: `??1CMDMPushConfiguration@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(CMDMPushConfiguration *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140007f34`
- `0x140018c44`

## callees

- `0x1400129a8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400129ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1400129ba`

## pseudocode

```c
void __fastcall CMDMPushConfiguration::~CMDMPushConfiguration(CMDMPushConfiguration *this)
{
  OLECHAR *v2; // rcx

  v2 = (OLECHAR *)*((_QWORD *)this + 1);
  if ( v2 )
    SysFreeString(v2);
  *((_DWORD *)this + 4) = 63;
}

```

## disassembly

```asm
0x1400129a8  push    rbx
0x1400129aa  sub     rsp, 20h
0x1400129ae  mov     rbx, rcx
0x1400129b1  mov     rcx, [rcx+8]; bstrString
0x1400129b5  test    rcx, rcx
0x1400129b8  jz      short loc_1400129C0
0x1400129ba  call    cs:__imp_SysFreeString
0x1400129c0  mov     dword ptr [rbx+10h], 3Fh ; '?'
0x1400129c7  add     rsp, 20h
0x1400129cb  pop     rbx
0x1400129cc  retn
```
