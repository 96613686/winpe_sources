# wistd::unique_ptr<MitigationOptionsPolicy::ImagePolicy,wistd::default_delete<MitigationOptionsPolicy::ImagePolicy>>::~unique_ptr<MitigationOptionsPolicy::ImagePolicy,wistd::default_delete<MitigationOptionsPolicy::ImagePolicy>>(void)

- ea: `0x180007720`
- end: `0x180007750`
- name: `??1?$unique_ptr@VImagePolicy@MitigationOptionsPolicy@@U?$default_delete@VImagePolicy@MitigationOptionsPolicy@@@wistd@@@wistd@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(MitigationOptionsPolicy::ImagePolicy **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000a5f0`

## callees

- `0x180002014`
- `0x180007720`
- `0x180007768`

## pseudocode

```c
void __fastcall wistd::unique_ptr<MitigationOptionsPolicy::ImagePolicy,wistd::default_delete<MitigationOptionsPolicy::ImagePolicy>>::~unique_ptr<MitigationOptionsPolicy::ImagePolicy,wistd::default_delete<MitigationOptionsPolicy::ImagePolicy>>(
        MitigationOptionsPolicy::ImagePolicy **a1)
{
  MitigationOptionsPolicy::ImagePolicy *v1; // rbx

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
  {
    MitigationOptionsPolicy::ImagePolicy::~ImagePolicy(v1);
    operator delete(v1, 0xD40u);
  }
}

```

## disassembly

```asm
0x180007720  push    rbx
0x180007722  sub     rsp, 20h
0x180007726  mov     rbx, [rcx]
0x180007729  mov     qword ptr [rcx], 0
0x180007730  test    rbx, rbx
0x180007733  jz      short loc_18000774A
0x180007735  mov     rcx, rbx; this
0x180007738  call    ??1ImagePolicy@MitigationOptionsPolicy@@QEAA@XZ; MitigationOptionsPolicy::ImagePolicy::~ImagePolicy(void)
0x18000773d  mov     edx, 0D40h; unsigned __int64
0x180007742  mov     rcx, rbx; void *
0x180007745  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000774a  add     rsp, 20h
0x18000774e  pop     rbx
0x18000774f  retn
```
