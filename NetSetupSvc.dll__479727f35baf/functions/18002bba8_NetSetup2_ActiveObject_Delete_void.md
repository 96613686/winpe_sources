# NetSetup2::ActiveObject::Delete(void)

- ea: `0x18002bba8`
- end: `0x18002bbf7`
- name: `?Delete@ActiveObject@NetSetup2@@QEAAXXZ`
- size: `79`
- prototype: `void __fastcall(NetSetup2::ActiveObject *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x18001de84`
- `0x18001f2e4`
- `0x180020384`
- `0x1800223a4`
- `0x18002266c`
- `0x180022800`
- `0x180023650`
- `0x18002fc96`
- `0x18002ff33`

## callees

- `0x1800032e4`
- `0x180008854`
- `0x18002bba8`

## import_xrefs

- `NetSetupApi!NetSetupDeleteObject` at `0x18002bbc7`
- `NetSetupApi!NetSetupDeleteObject` at `0x18002bbc7`

## pseudocode

```c
void __fastcall NetSetup2::ActiveObject::Delete(NetSetup2::ActiveObject *this)
{
  __int128 v1; // xmm0
  __int64 v2; // rdx
  _QWORD *v3; // rcx
  int v4; // eax
  __int128 v5; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE pExceptionObject[216]; // [rsp+30h] [rbp-D8h] BYREF

  v1 = *(_OWORD *)((char *)this + 20);
  v2 = *((unsigned int *)this + 4);
  v3 = *(_QWORD **)this;
  v5 = v1;
  v4 = NetSetupDeleteObject(*v3, v2, &v5);
  if ( v4 < 0 )
  {
    HResultException::HResultException((HResultException *)pExceptionObject, v4);
    throw (HResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18002bba8  sub     rsp, 108h
0x18002bbaf  movups  xmm0, xmmword ptr [rcx+14h]
0x18002bbb3  mov     edx, [rcx+10h]
0x18002bbb6  lea     r8, [rsp+108h+var_E8]
0x18002bbbb  mov     rcx, [rcx]
0x18002bbbe  movdqu  [rsp+108h+var_E8], xmm0
0x18002bbc4  mov     rcx, [rcx]
0x18002bbc7  call    cs:__imp_NetSetupDeleteObject
0x18002bbcd  test    eax, eax
0x18002bbcf  jns     short loc_18002BBEF
0x18002bbd1  mov     edx, eax; int
0x18002bbd3  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18002bbd8  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18002bbdd  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18002bbe4  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18002bbe9  call    _CxxThrowException_0
0x18002bbef  add     rsp, 108h
0x18002bbf6  retn
```
