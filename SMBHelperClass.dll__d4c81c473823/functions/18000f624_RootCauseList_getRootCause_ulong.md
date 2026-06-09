# RootCauseList::getRootCause(ulong)

- ea: `0x18000f624`
- end: `0x18000f67c`
- name: `?getRootCause@RootCauseList@@QEAAPEAVRootCause@@K@Z`
- size: `88`
- prototype: `struct RootCause *__fastcall(RootCauseList *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002974`
- `0x180005830`
- `0x1800067d0`
- `0x180008140`

## callees

- `0x18000257c`
- `0x18000f624`

## pseudocode

```c
struct RootCause *__fastcall RootCauseList::getRootCause(__int64 **this, unsigned int a2)
{
  __int64 *v2; // r8
  __int64 *v3; // rcx
  __int64 *v4; // rax
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  v2 = *this;
  v3 = v2;
  v4 = (__int64 *)v2[1];
  if ( *((_BYTE *)v4 + 25) )
    goto LABEL_9;
  do
  {
    if ( *((_DWORD *)v4 + 8) >= a2 )
    {
      v3 = v4;
      v4 = (__int64 *)*v4;
    }
    else
    {
      v4 = (__int64 *)v4[2];
    }
  }
  while ( !*((_BYTE *)v4 + 25) );
  if ( v3 == v2 || a2 < *((_DWORD *)v3 + 8) )
  {
LABEL_9:
    pExceptionObject = 4;
    throw (TestException *)&pExceptionObject;
  }
  return (struct RootCause *)v3[5];
}

```

## disassembly

```asm
0x18000f624  sub     rsp, 28h
0x18000f628  mov     r8, [rcx]
0x18000f62b  mov     rcx, r8
0x18000f62e  mov     rax, [r8+8]
0x18000f632  cmp     byte ptr [rax+19h], 0
0x18000f636  jnz     short loc_18000F662
0x18000f638  cmp     [rax+20h], edx
0x18000f63b  jnb     short loc_18000F643
0x18000f63d  mov     rax, [rax+10h]
0x18000f641  jmp     short loc_18000F649
0x18000f643  mov     rcx, rax
0x18000f646  mov     rax, [rax]
0x18000f649  cmp     byte ptr [rax+19h], 0
0x18000f64d  jz      short loc_18000F638
0x18000f64f  cmp     rcx, r8
0x18000f652  jz      short loc_18000F662
0x18000f654  cmp     edx, [rcx+20h]
0x18000f657  jb      short loc_18000F662
0x18000f659  mov     rax, [rcx+28h]
0x18000f65d  add     rsp, 28h
0x18000f661  retn
0x18000f662  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000f669  mov     [rsp+28h+pExceptionObject], 4
0x18000f671  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000f676  call    _CxxThrowException_0
```
