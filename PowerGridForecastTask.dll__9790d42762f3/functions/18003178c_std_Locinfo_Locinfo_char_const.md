# std::_Locinfo::_Locinfo(char const *)

- ea: `0x18003178c`
- end: `0x180031819`
- name: `??0_Locinfo@std@@QEAA@PEBD@Z`
- size: `141`
- prototype: `std::_Locinfo *__fastcall(std::_Locinfo *this, const char *)`
- caller_count: `39`
- callee_count: `5`
- tags: ``

## callers

- `0x18000392c`
- `0x1800039e0`
- `0x180003ab8`
- `0x180003b6c`
- `0x180003c20`
- `0x180005fe8`
- `0x18000c640`
- `0x18000c720`
- `0x18000c83c`
- `0x18000c958`
- `0x18000ca50`
- `0x18000cb04`
- `0x18000cbb8`
- `0x18000cc6c`
- `0x18000cd20`
- `0x18000cdd4`
- `0x18000ce88`
- `0x18000cf74`
- `0x18000d060`
- `0x18000d14c`
- `0x18000d238`
- `0x18000d2ec`
- `0x18000d3a0`
- `0x18000d454`
- `0x18000d508`
- `0x18000d5e4`
- `0x18000d6c0`
- `0x18000d798`
- `0x18000d870`
- `0x18001d820`
- `0x18001d93c`
- `0x18001d9f0`
- `0x18001daa4`
- `0x18001db58`
- `0x18001dc44`
- `0x18001dd30`
- `0x18001de08`
- `0x18003158c`
- `0x180033e38`

## callees

- `0x180002394`
- `0x1800026d8`
- `0x180026778`
- `0x18003178c`
- `0x180031888`

## pseudocode

```c
std::_Locinfo *__fastcall std::_Locinfo::_Locinfo(std::_Locinfo *this, const char *a2)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::_Lockit::_Lockit(this, 0);
  *((_QWORD *)this + 1) = 0;
  *((_BYTE *)this + 16) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_BYTE *)this + 32) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_WORD *)this + 24) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_WORD *)this + 32) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_BYTE *)this + 80) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_BYTE *)this + 96) = 0;
  if ( !a2 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "bad locale name");
    throw (std::runtime_error *)pExceptionObject;
  }
  std::_Locinfo::_Locinfo_ctor(this, a2);
  return this;
}

```

## disassembly

```asm
0x18003178c  mov     [rsp+arg_8], rbx
0x180031791  mov     [rsp+arg_0], rcx
0x180031796  push    rdi
0x180031797  sub     rsp, 40h
0x18003179b  mov     rdi, rdx
0x18003179e  mov     rbx, rcx
0x1800317a1  xor     edx, edx; int
0x1800317a3  call    ??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x1800317a8  nop
0x1800317a9  xor     ecx, ecx
0x1800317ab  mov     [rbx+8], rcx
0x1800317af  mov     [rbx+10h], cl
0x1800317b2  mov     [rbx+18h], rcx
0x1800317b6  mov     [rbx+20h], cl
0x1800317b9  mov     [rbx+28h], rcx
0x1800317bd  mov     [rbx+30h], cx
0x1800317c1  mov     [rbx+38h], rcx
0x1800317c5  mov     [rbx+40h], cx
0x1800317c9  mov     [rbx+48h], rcx
0x1800317cd  mov     [rbx+50h], cl
0x1800317d0  mov     [rbx+58h], rcx
0x1800317d4  mov     [rbx+60h], cl
0x1800317d7  test    rdi, rdi
0x1800317da  jz      short loc_1800317F6
0x1800317dc  mov     rdx, rdi; char *
0x1800317df  mov     rcx, rbx; struct std::_Locinfo *
0x1800317e2  call    ?_Locinfo_ctor@_Locinfo@std@@SAXPEAV12@PEBD@Z; std::_Locinfo::_Locinfo_ctor(std::_Locinfo *,char const *)
0x1800317e7  nop
0x1800317e8  mov     rax, rbx
0x1800317eb  mov     rbx, [rsp+48h+arg_8]
0x1800317f0  add     rsp, 40h
0x1800317f4  pop     rdi
0x1800317f5  retn
0x1800317f6  lea     rdx, aBadLocaleName; "bad locale name"
0x1800317fd  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180031802  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180031807  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18003180e  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180031813  call    _CxxThrowException_0
```
