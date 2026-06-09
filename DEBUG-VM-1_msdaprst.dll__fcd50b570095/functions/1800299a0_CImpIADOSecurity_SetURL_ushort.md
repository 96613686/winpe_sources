# CImpIADOSecurity::SetURL(ushort *)

- ea: `0x1800299a0`
- end: `0x180029a0c`
- name: `?SetURL@CImpIADOSecurity@@UEAAJPEAG@Z`
- size: `108`
- prototype: `int(CImpIADOSecurity *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015290`
- `0x180029248`

## callees

- `0x180029218`
- `0x1800292a4`
- `0x1800299a0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800299dd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800299dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800299c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800299c7`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::SetURL(struct CCriticalSection **this, unsigned __int16 *a2)
{
  OLECHAR *v4; // rcx
  BSTR v5; // rax
  unsigned int v6; // ebx
  char v8; // [rsp+30h] [rbp+8h] BYREF

  CMPCSAutoBlock::CMPCSAutoBlock((CMPCSAutoBlock *)&v8, this + 6);
  v4 = (OLECHAR *)this[4];
  if ( v4 )
  {
    SysFreeString(v4);
    this[4] = 0;
  }
  if ( !a2 || (v5 = SysAllocString(a2), (this[4] = (struct CCriticalSection *)v5) != 0) )
    v6 = 0;
  else
    v6 = -2147024882;
  CMPCSAutoBlock::~CMPCSAutoBlock((CMPCSAutoBlock *)&v8);
  return v6;
}

```

## disassembly

```asm
0x1800299a0  mov     [rsp+arg_8], rbx
0x1800299a5  push    rdi
0x1800299a6  sub     rsp, 20h
0x1800299aa  mov     rdi, rdx
0x1800299ad  mov     rbx, rcx
0x1800299b0  lea     rdx, [rcx+30h]; struct CCriticalSection **
0x1800299b4  lea     rcx, [rsp+28h+arg_0]; this
0x1800299b9  call    ??0CMPCSAutoBlock@@QEAA@PEAPEAVCCriticalSection@@@Z; CMPCSAutoBlock::CMPCSAutoBlock(CCriticalSection * *)
0x1800299be  mov     rcx, [rbx+20h]; bstrString
0x1800299c2  test    rcx, rcx
0x1800299c5  jz      short loc_1800299D5
0x1800299c7  call    cs:__imp_SysFreeString
0x1800299cd  mov     qword ptr [rbx+20h], 0
0x1800299d5  test    rdi, rdi
0x1800299d8  jz      short loc_1800299F3
0x1800299da  mov     rcx, rdi; psz
0x1800299dd  call    cs:__imp_SysAllocString
0x1800299e3  mov     [rbx+20h], rax
0x1800299e7  test    rax, rax
0x1800299ea  jnz     short loc_1800299F3
0x1800299ec  mov     ebx, 8007000Eh
0x1800299f1  jmp     short loc_1800299F5
0x1800299f3  xor     ebx, ebx
0x1800299f5  lea     rcx, [rsp+28h+arg_0]; this
0x1800299fa  call    ??1CMPCSAutoBlock@@QEAA@XZ; CMPCSAutoBlock::~CMPCSAutoBlock(void)
0x1800299ff  mov     eax, ebx
0x180029a01  mov     rbx, [rsp+28h+arg_8]
0x180029a06  add     rsp, 20h
0x180029a0a  pop     rdi
0x180029a0b  retn
```
