# StateRepository::Logging::EnableLog(bool)

- ea: `0x1800264d4`
- end: `0x180026505`
- name: `?EnableLog@Logging@StateRepository@@YAJ_N@Z`
- size: `49`
- prototype: `__int64 __fastcall(StateRepository::Logging *__hidden this, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002703c`
- `0x180028408`

## callees

- `0x1800264d4`

## import_xrefs

- `StateRepository.Core!sqlite3_config` at `0x1800264ee`
- `StateRepository.Core!sqlite3_config` at `0x1800264ee`

## pseudocode

```c
__int64 __fastcall StateRepository::Logging::EnableLog(StateRepository::Logging *this)
{
  __int64 result; // rax

  result = sqlite3_config(
             16,
             (unsigned __int64)StateRepository::Logging::sqliteLogCallback & -(__int64)((_BYTE)this != 0));
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x87AF0000;
  return result;
}

```

## disassembly

```asm
0x1800264d4  sub     rsp, 28h
0x1800264d8  neg     cl
0x1800264da  lea     rax, ?sqliteLogCallback@Logging@StateRepository@@YAXPEAXHPEBD@Z; StateRepository::Logging::sqliteLogCallback(void *,int,char const *)
0x1800264e1  sbb     rdx, rdx
0x1800264e4  xor     r8d, r8d
0x1800264e7  and     rdx, rax
0x1800264ea  lea     ecx, [r8+10h]
0x1800264ee  call    cs:__imp_sqlite3_config
0x1800264f4  test    eax, eax
0x1800264f6  jle     short loc_180026500
0x1800264f8  movzx   eax, ax
0x1800264fb  or      eax, 87AF0000h
0x180026500  add     rsp, 28h
0x180026504  retn
```
