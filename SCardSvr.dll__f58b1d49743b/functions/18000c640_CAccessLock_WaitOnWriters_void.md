# CAccessLock::WaitOnWriters(void)

- ea: `0x18000c640`
- end: `0x18000c69f`
- name: `?WaitOnWriters@CAccessLock@@IEAAXXZ`
- size: `95`
- prototype: `void __fastcall(CAccessLock *__hidden this)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180004c8c`
- `0x180005b2c`
- `0x1800067a0`
- `0x180007910`
- `0x18000f2a0`
- `0x18000f87c`
- `0x18000fcf0`
- `0x180010044`
- `0x1800106f0`
- `0x180010994`
- `0x180013740`

## callees

- `0x18000c640`
- `0x18000c870`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c654`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c654`

## pseudocode

```c
void __fastcall CAccessLock::WaitOnWriters(CAccessLock *this)
{
  __int64 v1; // rdi
  LPVOID Value; // rbx
  unsigned int v3; // eax
  ulong pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 11);
  Value = TlsGetValue(dword_18004B240);
  while ( 1 )
  {
    v3 = WaitForAnyObject(0xFFFFFFFF, v1, Value, 0);
    if ( v3 == 1 )
      break;
    if ( v3 == 2 )
    {
      pExceptionObject = -2146435070;
      throw &pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x18000c640  mov     [rsp+arg_8], rbx
0x18000c645  push    rdi
0x18000c646  sub     rsp, 20h
0x18000c64a  mov     rdi, [rcx+58h]
0x18000c64e  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000c654  call    cs:__imp_TlsGetValue
0x18000c65a  mov     rbx, rax
0x18000c65d  xor     r9d, r9d
0x18000c660  mov     r8, rbx
0x18000c663  mov     rdx, rdi
0x18000c666  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x18000c66b  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x18000c670  cmp     eax, 1
0x18000c673  jnz     short loc_18000C680
0x18000c675  mov     rbx, [rsp+28h+arg_8]
0x18000c67a  add     rsp, 20h
0x18000c67e  pop     rdi
0x18000c67f  retn
0x18000c680  cmp     eax, 2
0x18000c683  jnz     short loc_18000C65D
0x18000c685  lea     rdx, _TI1K; pThrowInfo
0x18000c68c  mov     [rsp+28h+pExceptionObject], 80100002h
0x18000c694  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c699  call    _CxxThrowException_0
```
