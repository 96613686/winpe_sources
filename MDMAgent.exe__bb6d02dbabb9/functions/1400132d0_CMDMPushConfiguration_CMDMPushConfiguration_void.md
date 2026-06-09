# CMDMPushConfiguration::~CMDMPushConfiguration(void)

- ea: `0x1400132d0`
- end: `0x1400132fc`
- name: `??1CMDMPushConfiguration@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(CMDMPushConfiguration *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000829c`
- `0x1400199a5`

## callees

- `0x1400132d0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400132e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400132e2`

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
0x1400132d0  push    rbx
0x1400132d2  sub     rsp, 20h
0x1400132d6  mov     rbx, rcx
0x1400132d9  mov     rcx, [rcx+8]; bstrString
0x1400132dd  test    rcx, rcx
0x1400132e0  jz      short loc_1400132EE
0x1400132e2  call    cs:__imp_SysFreeString
0x1400132e9  nop     dword ptr [rax+rax+00h]
0x1400132ee  mov     dword ptr [rbx+10h], 3Fh ; '?'
0x1400132f5  add     rsp, 20h
0x1400132f9  pop     rbx
0x1400132fa  retn
```
