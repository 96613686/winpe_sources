# SerializedRegistryKey::InitReadKey(HKEY__ *)

- ea: `0x180010754`
- end: `0x1800107e2`
- name: `?InitReadKey@SerializedRegistryKey@@AEAAXPEAUHKEY__@@@Z`
- size: `142`
- prototype: `void __fastcall(SerializedRegistryKey *this, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180021638`

## callees

- `0x180010754`
- `0x1800107e8`
- `0x180011a64`
- `0x180020040`
- `0x180020edc`

## pseudocode

```c
void __fastcall SerializedRegistryKey::InitReadKey(SerializedRegistryKey *this, HKEY a2)
{
  RegistryKey *v4; // rax
  const unsigned __int16 *v5; // r8
  __int64 *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // [rsp+38h] [rbp-20h] BYREF
  std::tr1::_Ref_count_base *v10; // [rsp+40h] [rbp-18h]

  v4 = (RegistryKey *)operator new(0x50u);
  if ( v4 )
  {
    v5 = (const unsigned __int16 *)((char *)this + 80);
    if ( *((_QWORD *)this + 13) >= 8u )
      v5 = *(const unsigned __int16 **)v5;
    RegistryKey::RegistryKey(v4, a2, v5);
  }
  v6 = std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(&v9);
  v7 = v6[1];
  v6[1] = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = v7;
  v8 = *v6;
  *v6 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = v8;
  if ( v10 )
    std::tr1::_Ref_count_base::_Decref(v10);
}

```

## disassembly

```asm
0x180010754  push    rdi
0x180010756  sub     rsp, 50h
0x18001075a  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x180010763  mov     [rsp+58h+arg_8], rbx
0x180010768  mov     rdi, rdx
0x18001076b  mov     rbx, rcx
0x18001076e  mov     ecx, 50h ; 'P'; Size
0x180010773  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010778  mov     [rsp+58h+arg_0], rax
0x18001077d  test    rax, rax
0x180010780  jz      short loc_18001079C
0x180010782  lea     r8, [rbx+50h]
0x180010786  cmp     qword ptr [r8+18h], 8
0x18001078b  jb      short loc_180010790
0x18001078d  mov     r8, [r8]; unsigned __int16 *
0x180010790  mov     rdx, rdi; HKEY
0x180010793  mov     rcx, rax; this
0x180010796  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@PEBGKK@Z; RegistryKey::RegistryKey(HKEY__ *,ushort const *,ulong,ulong)
0x18001079b  nop
0x18001079c  mov     rdx, rax
0x18001079f  lea     rcx, [rsp+58h+var_20]
0x1800107a4  call    ??$?0VRegistryKey@@@?$shared_ptr@VIRegistryKey@@@tr1@std@@QEAA@PEAVRegistryKey@@@Z; std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(RegistryKey *)
0x1800107a9  mov     rdx, [rax+8]
0x1800107ad  mov     rcx, [rbx+48h]
0x1800107b1  mov     [rax+8], rcx
0x1800107b5  mov     [rbx+48h], rdx
0x1800107b9  mov     rdx, [rax]
0x1800107bc  mov     rcx, [rbx+40h]
0x1800107c0  mov     [rax], rcx
0x1800107c3  mov     [rbx+40h], rdx
0x1800107c7  mov     rcx, [rsp+58h+var_18]; this
0x1800107cc  test    rcx, rcx
0x1800107cf  jz      short loc_1800107D7
0x1800107d1  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x1800107d6  nop
0x1800107d7  mov     rbx, [rsp+58h+arg_8]
0x1800107dc  add     rsp, 50h
0x1800107e0  pop     rdi
0x1800107e1  retn
```
