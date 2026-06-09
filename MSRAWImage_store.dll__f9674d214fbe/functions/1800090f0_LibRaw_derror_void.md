# LibRaw::derror(void)

- ea: `0x1800090f0`
- end: `0x1800091d0`
- name: `?derror@LibRaw@@IEAAXXZ`
- size: `224`
- prototype: `void __fastcall(LibRaw *__hidden this)`
- caller_count: `40`
- callee_count: `3`
- tags: ``

## callers

- `0x1800125e0`
- `0x1800146a0`
- `0x180014da0`
- `0x180021a40`
- `0x180021dc0`
- `0x180029920`
- `0x180029b50`
- `0x180029d00`
- `0x18002a9b0`
- `0x18002c4d0`
- `0x18002c660`
- `0x18002c950`
- `0x180045470`
- `0x180046110`
- `0x1800463c0`
- `0x180046f40`
- `0x1800478f0`
- `0x180047cf0`
- `0x180048c00`
- `0x180048e20`
- `0x180049730`
- `0x180049aa0`
- `0x18004a530`
- `0x18004aa70`
- `0x18004ad50`
- `0x18004b4f0`
- `0x18004b700`
- `0x18004be80`
- `0x18004cc00`
- `0x18004ce80`
- `0x18004ffd0`
- `0x180050310`
- `0x180053070`
- `0x18005bcb0`
- `0x18005c210`
- `0x18005c430`
- `0x18005c6c0`
- `0x18005c950`
- `0x18005d680`
- `0x18005d980`

## callees

- `0x180003e4c`
- `0x1800090f0`
- `0x1800b4010`

## pseudocode

```c
void __fastcall LibRaw::derror(LibRaw *this)
{
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rax
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_DWORD *)this + 95385) )
  {
    v2 = *((_QWORD *)this + 47659);
    if ( v2 )
    {
      v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 72LL))(v2);
      v4 = *((_QWORD *)this + 95880);
      if ( v3 )
      {
        if ( v4 )
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 112LL))(*((_QWORD *)this + 47659));
          (*((void (__fastcall **)(_QWORD, __int64, __int64))this + 95880))(*((_QWORD *)this + 95881), v7, 0xFFFFFFFFLL);
        }
        pExceptionObject = 4;
        throw (LibRaw_exceptions *)&pExceptionObject;
      }
      if ( v4 )
      {
        v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 32LL))(*((_QWORD *)this + 47659));
        v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 112LL))(*((_QWORD *)this + 47659));
        (*((void (__fastcall **)(_QWORD, __int64, _QWORD))this + 95880))(*((_QWORD *)this + 95881), v6, v5);
      }
    }
  }
  ++*((_DWORD *)this + 95385);
}

```

## disassembly

```asm
0x1800090f0  push    rdi
0x1800090f2  sub     rsp, 20h
0x1800090f6  cmp     dword ptr [rcx+5D264h], 0
0x1800090fd  mov     rdi, rcx
0x180009100  jnz     short loc_180009176
0x180009102  mov     rcx, [rcx+5D158h]
0x180009109  test    rcx, rcx
0x18000910c  jz      short loc_180009176
0x18000910e  mov     rax, [rcx]
0x180009111  mov     rax, [rax+48h]
0x180009115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000911a  mov     rcx, [rdi+0BB440h]
0x180009121  test    eax, eax
0x180009123  jnz     short loc_180009182
0x180009125  test    rcx, rcx
0x180009128  jz      short loc_180009176
0x18000912a  mov     rcx, [rdi+5D158h]
0x180009131  mov     [rsp+28h+arg_8], rbx
0x180009136  mov     rax, [rcx]
0x180009139  mov     rax, [rax+20h]
0x18000913d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009142  mov     rcx, [rdi+5D158h]
0x180009149  mov     rbx, rax
0x18000914c  mov     rdx, [rcx]
0x18000914f  mov     rax, [rdx+70h]
0x180009153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009158  mov     rcx, [rdi+0BB448h]
0x18000915f  mov     rdx, rax
0x180009162  mov     rax, [rdi+0BB440h]
0x180009169  mov     r8d, ebx
0x18000916c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009171  mov     rbx, [rsp+28h+arg_8]
0x180009176  inc     dword ptr [rdi+5D264h]
0x18000917c  add     rsp, 20h
0x180009180  pop     rdi
0x180009181  retn
0x180009182  test    rcx, rcx
0x180009185  jz      short loc_1800091B6
0x180009187  mov     rcx, [rdi+5D158h]
0x18000918e  mov     rax, [rcx]
0x180009191  mov     rax, [rax+70h]
0x180009195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000919a  mov     rcx, [rdi+0BB448h]
0x1800091a1  mov     rdx, rax
0x1800091a4  mov     rax, [rdi+0BB440h]
0x1800091ab  mov     r8d, 0FFFFFFFFh
0x1800091b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091b6  lea     rdx, _TI1?AW4LibRaw_exceptions@@; pThrowInfo
0x1800091bd  mov     [rsp+28h+pExceptionObject], 4
0x1800091c5  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800091ca  call    _CxxThrowException
```
