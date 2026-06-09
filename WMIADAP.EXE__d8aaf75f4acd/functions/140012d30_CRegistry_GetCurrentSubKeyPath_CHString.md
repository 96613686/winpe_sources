# CRegistry::GetCurrentSubKeyPath(CHString &)

- ea: `0x140012d30`
- end: `0x140012def`
- name: `?GetCurrentSubKeyPath@CRegistry@@QEAAKAEAVCHString@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(CRegistry *this, struct CHString *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140013440`

## callees

- `0x14000fe30`
- `0x14000ff40`
- `0x14000ffc0`
- `0x140010230`
- `0x140010bc0`
- `0x140012c70`
- `0x140012d30`

## pseudocode

```c
__int64 __fastcall CRegistry::GetCurrentSubKeyPath(CRegistry *this, struct CHString *a2)
{
  unsigned int CurrentSubKeyName; // ebx
  const unsigned __int16 **v5; // rax
  const unsigned __int16 *v7; // [rsp+20h] [rbp-18h] BYREF
  const unsigned __int16 *v8[2]; // [rsp+28h] [rbp-10h] BYREF
  const unsigned __int16 *v9; // [rsp+50h] [rbp+18h] BYREF
  const unsigned __int16 *v10; // [rsp+58h] [rbp+20h] BYREF

  v9 = afxPchNil;
  CHString::CHString((CHString *)&v10, L"\\");
  CurrentSubKeyName = CRegistry::GetCurrentSubKeyName(this, (struct CHString *)&v9);
  if ( CurrentSubKeyName )
  {
    CHString::Empty(a2);
  }
  else
  {
    operator+((CHString *)v8);
    v5 = (const unsigned __int16 **)operator+((CHString *)&v7);
    CHString::operator=((const unsigned __int16 **)a2, v5);
    CHString::~CHString(&v7);
    CHString::~CHString(v8);
  }
  CHString::~CHString(&v10);
  CHString::~CHString(&v9);
  return CurrentSubKeyName;
}

```

## disassembly

```asm
0x140012d30  mov     r11, rsp
0x140012d33  mov     [r11+8], rbx
0x140012d37  mov     [r11+10h], rsi
0x140012d3b  push    rdi
0x140012d3c  sub     rsp, 30h
0x140012d40  mov     rdi, rdx
0x140012d43  mov     rsi, rcx
0x140012d46  mov     rax, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x140012d4d  mov     [r11+18h], rax
0x140012d51  lea     rdx, asc_14001A9B8; "\\"
0x140012d58  lea     rcx, [r11+20h]; this
0x140012d5c  call    ??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x140012d61  nop
0x140012d62  lea     rdx, [rsp+38h+arg_10]; struct CHString *
0x140012d67  mov     rcx, rsi; this
0x140012d6a  call    ?GetCurrentSubKeyName@CRegistry@@QEAAKAEAVCHString@@@Z; CRegistry::GetCurrentSubKeyName(CHString &)
0x140012d6f  mov     ebx, eax
0x140012d71  test    eax, eax
0x140012d73  jnz     short loc_140012DBF
0x140012d75  lea     rdx, [rsi+18h]
0x140012d79  lea     r8, [rsp+38h+arg_18]
0x140012d7e  lea     rcx, [rsp+38h+var_10]; this
0x140012d83  call    ??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x140012d88  nop
0x140012d89  lea     r8, [rsp+38h+arg_10]
0x140012d8e  mov     rdx, rax
0x140012d91  lea     rcx, [rsp+38h+var_18]; this
0x140012d96  call    ??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x140012d9b  nop
0x140012d9c  mov     rdx, rax
0x140012d9f  mov     rcx, rdi; this
0x140012da2  call    ??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x140012da7  nop
0x140012da8  lea     rcx, [rsp+38h+var_18]; this
0x140012dad  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140012db2  nop
0x140012db3  lea     rcx, [rsp+38h+var_10]; this
0x140012db8  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140012dbd  jmp     short loc_140012DC8
0x140012dbf  mov     rcx, rdi; this
0x140012dc2  call    ?Empty@CHString@@QEAAXXZ; CHString::Empty(void)
0x140012dc7  nop
0x140012dc8  lea     rcx, [rsp+38h+arg_18]; this
0x140012dcd  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140012dd2  nop
0x140012dd3  lea     rcx, [rsp+38h+arg_10]; this
0x140012dd8  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140012ddd  mov     eax, ebx
0x140012ddf  mov     rbx, [rsp+38h+arg_0]
0x140012de4  mov     rsi, [rsp+38h+arg_8]
0x140012de9  add     rsp, 30h
0x140012ded  pop     rdi
0x140012dee  retn
```
