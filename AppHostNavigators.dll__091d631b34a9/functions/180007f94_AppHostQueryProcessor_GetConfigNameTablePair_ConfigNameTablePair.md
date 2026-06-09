# AppHostQueryProcessor::GetConfigNameTablePair(ConfigNameTablePair * *)

- ea: `0x180007f94`
- end: `0x180008030`
- name: `?GetConfigNameTablePair@AppHostQueryProcessor@@AEAAJPEAPEAVConfigNameTablePair@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(AppHostQueryProcessor *__hidden this, struct ConfigNameTablePair **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008190`

## callees

- `0x180001194`
- `0x180003a1c`
- `0x1800075f4`
- `0x180007f94`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppHostQueryProcessor::GetConfigNameTablePair(
        AppHostQueryProcessor *this,
        struct ConfigNameTablePair **a2)
{
  volatile signed __int32 **v2; // rdi
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v5; // rax

  v2 = (volatile signed __int32 **)((char *)this + 32);
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( !v4 )
  {
    v5 = (volatile signed __int32 *)operator new(0x90u);
    v4 = v5;
    if ( v5 )
    {
      *(_QWORD *)v5 = &InvasivePtrObject::`vftable';
      *((_DWORD *)v5 + 2) = 1;
      *(_QWORD *)v5 = &ConfigNameTablePair::`vftable';
      ConfigNameTablePair::InternalTable::InternalTable(
        (ConfigNameTablePair::InternalTable *)(v5 + 4),
        (struct ConfigNameTablePair *)v5);
      ConfigNameTablePair::InternalTable::InternalTable(
        (ConfigNameTablePair::InternalTable *)(v4 + 20),
        (struct ConfigNameTablePair *)v4);
    }
    else
    {
      v4 = 0;
    }
    InvasivePtr<ConfigLocationsTree>::Reset(v2);
    *v2 = v4;
    if ( !v4 )
      return 2147942414LL;
  }
  *a2 = (struct ConfigNameTablePair *)v4;
  _InterlockedIncrement(v4 + 2);
  return 0;
}

```

## disassembly

```asm
0x180007f94  mov     [rsp+arg_8], rbx
0x180007f99  mov     [rsp+arg_10], rsi
0x180007f9e  push    rdi
0x180007f9f  sub     rsp, 20h
0x180007fa3  lea     rdi, [rcx+20h]
0x180007fa7  mov     rsi, rdx
0x180007faa  mov     rbx, [rdi]
0x180007fad  test    rbx, rbx
0x180007fb0  jnz     short loc_180008017
0x180007fb2  mov     ecx, 90h; Size
0x180007fb7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007fbc  mov     [rsp+28h+arg_0], rax
0x180007fc1  mov     rbx, rax
0x180007fc4  test    rax, rax
0x180007fc7  jz      short loc_180007FFE
0x180007fc9  lea     rax, ??_7InvasivePtrObject@@6B@; const InvasivePtrObject::`vftable'
0x180007fd0  mov     rdx, rbx; struct ConfigNameTablePair *
0x180007fd3  mov     [rbx], rax
0x180007fd6  lea     rcx, [rbx+10h]; this
0x180007fda  lea     rax, ??_7ConfigNameTablePair@@6B@; const ConfigNameTablePair::`vftable'
0x180007fe1  mov     dword ptr [rbx+8], 1
0x180007fe8  mov     [rbx], rax
0x180007feb  call    ??0InternalTable@ConfigNameTablePair@@QEAA@PEAV1@@Z; ConfigNameTablePair::InternalTable::InternalTable(ConfigNameTablePair *)
0x180007ff0  lea     rcx, [rbx+50h]; this
0x180007ff4  mov     rdx, rbx; struct ConfigNameTablePair *
0x180007ff7  call    ??0InternalTable@ConfigNameTablePair@@QEAA@PEAV1@@Z; ConfigNameTablePair::InternalTable::InternalTable(ConfigNameTablePair *)
0x180007ffc  jmp     short loc_180008000
0x180007ffe  xor     ebx, ebx
0x180008000  mov     rcx, rdi
0x180008003  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180008008  mov     [rdi], rbx
0x18000800b  test    rbx, rbx
0x18000800e  jnz     short loc_180008017
0x180008010  mov     eax, 8007000Eh
0x180008015  jmp     short loc_180008020
0x180008017  mov     [rsi], rbx
0x18000801a  lock inc dword ptr [rbx+8]
0x18000801e  xor     eax, eax
0x180008020  mov     rbx, [rsp+28h+arg_8]
0x180008025  mov     rsi, [rsp+28h+arg_10]
0x18000802a  add     rsp, 20h
0x18000802e  pop     rdi
0x18000802f  retn
```
