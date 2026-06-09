# CommonUtil::CMpVersionDllWrapper::`scalar deleting destructor'(uint)

- ea: `0x1400054e8`
- end: `0x14000556c`
- name: `??_GCMpVersionDllWrapper@CommonUtil@@QEAAPEAXI@Z`
- size: `132`
- prototype: `void *__fastcall(CommonUtil::CMpVersionDllWrapper *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140005570`

## callees

- `0x1400054e8`
- `0x140005c40`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140005545`
- `KERNEL32!FreeLibrary` at `0x140005545`

## pseudocode

```c
CommonUtil::CMpVersionDllWrapper *__fastcall CommonUtil::CMpVersionDllWrapper::`scalar deleting destructor'(
        HMODULE *this,
        char a2)
{
  HMODULE v4; // rcx

  off_14003B110[0] = CommonUtil::VerQueryValueWNotInitialized;
  off_14003B118[0] = CommonUtil::VerQueryValueWNotInitialized;
  off_14003B120[0] = CommonUtil::VerQueryValueWNotInitialized;
  off_14003B128 = CommonUtil::GetFileVersionInfoSizeExWDownlevel;
  off_14003B130 = CommonUtil::GetFileVersionInfoExWDownlevel;
  v4 = *this;
  if ( v4 )
    FreeLibrary(v4);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return (CommonUtil::CMpVersionDllWrapper *)this;
}

```

## disassembly

```asm
0x1400054e8  mov     [rsp+arg_0], rbx
0x1400054ed  push    rdi
0x1400054ee  sub     rsp, 20h
0x1400054f2  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x1400054f9  mov     rbx, rcx
0x1400054fc  mov     cs:off_14003B110, rax
0x140005503  mov     edi, edx
0x140005505  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x14000550c  mov     cs:off_14003B118, rax
0x140005513  lea     rax, CommonUtil__VerQueryValueWNotInitialized
0x14000551a  mov     cs:off_14003B120, rax
0x140005521  lea     rax, CommonUtil__GetFileVersionInfoSizeExWDownlevel
0x140005528  mov     cs:off_14003B128, rax
0x14000552f  lea     rax, CommonUtil__GetFileVersionInfoExWDownlevel
0x140005536  mov     cs:off_14003B130, rax
0x14000553d  mov     rcx, [rcx]; hLibModule
0x140005540  test    rcx, rcx
0x140005543  jz      short loc_14000554B
0x140005545  call    cs:__imp_FreeLibrary
0x14000554b  test    dil, 1
0x14000554f  jz      short loc_14000555E
0x140005551  mov     edx, 8; unsigned __int64
0x140005556  mov     rcx, rbx; void *
0x140005559  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000555e  mov     rax, rbx
0x140005561  mov     rbx, [rsp+28h+arg_0]
0x140005566  add     rsp, 20h
0x14000556a  pop     rdi
0x14000556b  retn
```
