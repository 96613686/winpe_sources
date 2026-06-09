# MitigationOptionsPolicy::ImagePolicy::~ImagePolicy(void)

- ea: `0x180007768`
- end: `0x180007847`
- name: `??1ImagePolicy@MitigationOptionsPolicy@@QEAA@XZ`
- size: `223`
- prototype: `void __fastcall(char **this)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007720`
- `0x180009f70`
- `0x18000a5f0`
- `0x180011028`
- `0x18001208c`
- `0x1800120e4`
- `0x1800121a0`
- `0x1800121d4`
- `0x1800127a8`
- `0x180013f90`
- `0x180013fc6`

## callees

- `0x1800076b4`

## pseudocode

```c
void __fastcall MitigationOptionsPolicy::ImagePolicy::~ImagePolicy(char **this)
{
  std::wstring::~wstring(this + 417);
  std::wstring::~wstring(this + 409);
  std::wstring::~wstring(this + 397);
  std::wstring::~wstring(this + 389);
  std::wstring::~wstring(this + 381);
  std::wstring::~wstring(this + 373);
  std::wstring::~wstring(this + 99);
  std::wstring::~wstring(this + 87);
  std::wstring::~wstring(this + 79);
  std::wstring::~wstring(this + 69);
  std::wstring::~wstring(this + 59);
  std::wstring::~wstring(this + 51);
  std::wstring::~wstring(this + 43);
  std::wstring::~wstring(this + 33);
  std::wstring::~wstring(this + 25);
  std::wstring::~wstring(this + 17);
  std::wstring::~wstring(this + 5);
  std::wstring::~wstring(this);
}

```

## disassembly

```asm
0x180007768  push    rbx
0x18000776a  sub     rsp, 20h
0x18000776e  mov     rbx, rcx
0x180007771  add     rcx, 0D08h
0x180007778  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000777d  lea     rcx, [rbx+0CC8h]
0x180007784  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007789  lea     rcx, [rbx+0C68h]
0x180007790  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007795  lea     rcx, [rbx+0C28h]
0x18000779c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800077a1  lea     rcx, [rbx+0BE8h]
0x1800077a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800077ad  lea     rcx, [rbx+0BA8h]
0x1800077b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800077b9  lea     rcx, [rbx+318h]
0x1800077c0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800077c5  lea     rcx, [rbx+2B8h]
0x1800077cc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800077d1  lea     rcx, [rbx+278h]
0x1800077d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800077dd  lea     rcx, [rbx+228h]
0x1800077e4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800077e9  lea     rcx, [rbx+1D8h]
0x1800077f0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800077f5  lea     rcx, [rbx+198h]
0x1800077fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007801  lea     rcx, [rbx+158h]
0x180007808  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000780d  lea     rcx, [rbx+108h]
0x180007814  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007819  lea     rcx, [rbx+0C8h]
0x180007820  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007825  lea     rcx, [rbx+88h]
0x18000782c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007831  lea     rcx, [rbx+28h]
0x180007835  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000783a  mov     rcx, rbx
0x18000783d  add     rsp, 20h
0x180007841  pop     rbx
0x180007842  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
