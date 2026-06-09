# CVdsShrinkWrapper::Wait(long *,_VDS_ASYNC_OUTPUT *)

- ea: `0x18000ce40`
- end: `0x18000ced5`
- name: `?Wait@CVdsShrinkWrapper@@UEAAJPEAJPEAU_VDS_ASYNC_OUTPUT@@@Z`
- size: `149`
- prototype: `__int64 __fastcall(CVdsShrinkWrapper *__hidden this, int *, struct _VDS_ASYNC_OUTPUT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ce40`

## import_xrefs

- `msvcrt!_beginthread` at `0x18000ce76`
- `msvcrt!_beginthread` at `0x18000ce76`
- `KERNEL32!WaitForSingleObject` at `0x18000ce87`
- `KERNEL32!WaitForSingleObject` at `0x18000ce87`

## pseudocode

```c
__int64 __fastcall CVdsShrinkWrapper::Wait(CVdsShrinkWrapper *this, int *a2, struct _VDS_ASYNC_OUTPUT *a3)
{
  unsigned int v6; // esi
  __int64 v7; // rax
  __int64 v8; // rcx

  v6 = 0;
  v7 = *((_QWORD *)this + 1);
  if ( v7 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 60));
    _beginthread((_beginthread_proc_type)CVdsShrinkWrapper::AsyncWait_Thread, 0, *((void **)this + 1));
    WaitForSingleObject(*(HANDLE *)(*((_QWORD *)this + 1) + 48LL), 0xFFFFFFFF);
    if ( *(_DWORD *)(*((_QWORD *)this + 1) + 56LL) == 1 )
    {
      *a2 = -2147023673;
      *(_OWORD *)&a3->type = 0;
      *(_OWORD *)(&a3->cvd + 1) = 0;
    }
    else
    {
      *a2 = *(_DWORD *)(*((_QWORD *)this + 1) + 8LL);
      v8 = *((_QWORD *)this + 1);
      *(_OWORD *)&a3->type = *(_OWORD *)(v8 + 16);
      *(_OWORD *)(&a3->cvd + 1) = *(_OWORD *)(v8 + 32);
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return v6;
}

```

## disassembly

```asm
0x18000ce40  push    rbx
0x18000ce42  push    rsi
0x18000ce43  push    rdi
0x18000ce44  push    r14
0x18000ce46  sub     rsp, 28h
0x18000ce4a  mov     rbx, r8
0x18000ce4d  mov     r14, rdx
0x18000ce50  mov     rdi, rcx
0x18000ce53  xor     esi, esi
0x18000ce55  mov     rax, [rcx+8]
0x18000ce59  test    rax, rax
0x18000ce5c  jnz     short loc_18000CE65
0x18000ce5e  mov     esi, 8000FFFFh
0x18000ce63  jmp     short loc_18000CEC9
0x18000ce65  lock inc dword ptr [rax+3Ch]
0x18000ce69  mov     r8, [rcx+8]; ArgList
0x18000ce6d  xor     edx, edx; StackSize
0x18000ce6f  lea     rcx, ?AsyncWait_Thread@CVdsShrinkWrapper@@CAXPEAX@Z; StartAddress
0x18000ce76  call    cs:__imp__beginthread
0x18000ce7c  mov     rcx, [rdi+8]
0x18000ce80  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ce83  mov     rcx, [rcx+30h]; hHandle
0x18000ce87  call    cs:__imp_WaitForSingleObject
0x18000ce8d  mov     rax, [rdi+8]
0x18000ce91  mov     ecx, [rax+38h]
0x18000ce94  cmp     ecx, 1
0x18000ce97  jnz     short loc_18000CEAC
0x18000ce99  mov     dword ptr [r14], 800704C7h
0x18000cea0  xorps   xmm0, xmm0
0x18000cea3  movups  xmmword ptr [rbx], xmm0
0x18000cea6  movups  xmmword ptr [rbx+10h], xmm0
0x18000ceaa  jmp     short loc_18000CEC9
0x18000ceac  mov     rax, [rdi+8]
0x18000ceb0  mov     ecx, [rax+8]
0x18000ceb3  mov     [r14], ecx
0x18000ceb6  mov     rcx, [rdi+8]
0x18000ceba  movups  xmm0, xmmword ptr [rcx+10h]
0x18000cebe  movups  xmmword ptr [rbx], xmm0
0x18000cec1  movups  xmm1, xmmword ptr [rcx+20h]
0x18000cec5  movups  xmmword ptr [rbx+10h], xmm1
0x18000cec9  mov     eax, esi
0x18000cecb  add     rsp, 28h
0x18000cecf  pop     r14
0x18000ced1  pop     rdi
0x18000ced2  pop     rsi
0x18000ced3  pop     rbx
0x18000ced4  retn
0x180014149  push    rbp
0x18001414b  sub     rsp, 20h
0x18001414f  mov     rbp, rdx
0x180014152  add     rsp, 20h
0x180014156  pop     rbp
0x180014157  retn
```
