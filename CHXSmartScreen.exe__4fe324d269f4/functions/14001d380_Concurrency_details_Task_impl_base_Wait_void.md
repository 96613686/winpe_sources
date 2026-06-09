# Concurrency::details::_Task_impl_base::_Wait(void)

- ea: `0x14001d380`
- end: `0x14001d456`
- name: `?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ`
- size: `214`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140015f1c`
- `0x1400165e4`
- `0x140017770`

## callees

- `0x140003330`
- `0x140015024`
- `0x14001cce8`
- `0x14001d380`
- `0x140031960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14001d3d8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14001d3d8`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x14001d3b2`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x14001d3b2`

## string_xrefs

- `0x14001d433`: `Illegal to wait on a task in a Windows Runtime STA`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl_base::_Wait(__int64 a1)
{
  Concurrency::details::_ExceptionHolder *v2; // rcx
  __int64 result; // rax
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-58h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+58h] [rbp-20h] BYREF
  APTTYPE pAptType; // [rsp+5Ch] [rbp-1Ch] BYREF

  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  if ( CoGetApartmentType(&pAptType, &pAptQualifier) < 0 )
    goto LABEL_5;
  if ( pAptType )
  {
    if ( pAptType == APTTYPE_NA )
    {
      if ( ((pAptQualifier - 3) & 0xFFFFFFFD) != 0 )
        goto LABEL_5;
    }
    else if ( pAptType != APTTYPE_MAINSTA )
    {
LABEL_5:
      WaitForSingleObjectEx(*(HANDLE *)(a1 + 8), 0xFFFFFFFF, 0);
      goto LABEL_6;
    }
  }
  if ( *(_DWORD *)(a1 + 16) != 3 && *(_DWORD *)(a1 + 16) != 4 )
  {
    pplx::invalid_operation::invalid_operation(
      (pplx::invalid_operation *)pExceptionObject,
      "Illegal to wait on a task in a Windows Runtime STA");
    throw (pplx::invalid_operation *)pExceptionObject;
  }
LABEL_6:
  v2 = *(Concurrency::details::_ExceptionHolder **)(a1 + 24);
  if ( v2 )
  {
    Concurrency::details::_ExceptionHolder::_RethrowUserException(v2);
  }
  else
  {
    result = 2;
    if ( *(_DWORD *)(a1 + 16) == 4 )
      return result;
  }
  return 1;
}

```

## disassembly

```asm
0x14001d380  push    rbx
0x14001d382  sub     rsp, 70h
0x14001d386  mov     rax, cs:__security_cookie
0x14001d38d  xor     rax, rsp
0x14001d390  mov     [rsp+78h+var_18], rax
0x14001d395  mov     rbx, rcx
0x14001d398  mov     [rsp+78h+pAptType], 0
0x14001d3a0  mov     [rsp+78h+pAptQualifier], 0
0x14001d3a8  lea     rdx, [rsp+78h+pAptQualifier]; pAptQualifier
0x14001d3ad  lea     rcx, [rsp+78h+pAptType]; pAptType
0x14001d3b2  call    cs:__imp_CoGetApartmentType
0x14001d3b8  test    eax, eax
0x14001d3ba  js      short loc_14001D3CE
0x14001d3bc  mov     ecx, [rsp+78h+pAptType]
0x14001d3c0  test    ecx, ecx
0x14001d3c2  jz      short loc_14001D3FC
0x14001d3c4  sub     ecx, 2
0x14001d3c7  jz      short loc_14001D3EE
0x14001d3c9  cmp     ecx, 1
0x14001d3cc  jz      short loc_14001D3FC
0x14001d3ce  xor     r8d, r8d; bAlertable
0x14001d3d1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001d3d4  mov     rcx, [rbx+8]; hHandle
0x14001d3d8  call    cs:__imp_WaitForSingleObjectEx
0x14001d3de  mov     rcx, [rbx+18h]; this
0x14001d3e2  test    rcx, rcx
0x14001d3e5  jz      short loc_14001D40E
0x14001d3e7  call    ?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ; Concurrency::details::_ExceptionHolder::_RethrowUserException(void)
0x14001d3ec  jmp     short loc_14001D41B
0x14001d3ee  mov     eax, [rsp+78h+pAptQualifier]
0x14001d3f2  add     eax, 0FFFFFFFDh
0x14001d3f5  test    eax, 0FFFFFFFDh
0x14001d3fa  jnz     short loc_14001D3CE
0x14001d3fc  mov     eax, [rbx+10h]
0x14001d3ff  cmp     eax, 3
0x14001d402  jz      short loc_14001D3DE
0x14001d404  mov     eax, [rbx+10h]
0x14001d407  cmp     eax, 4
0x14001d40a  jnz     short loc_14001D433
0x14001d40c  jmp     short loc_14001D3DE
0x14001d40e  mov     ecx, [rbx+10h]
0x14001d411  cmp     ecx, 4
0x14001d414  mov     eax, 2
0x14001d419  jz      short loc_14001D420
0x14001d41b  mov     eax, 1
0x14001d420  mov     rcx, [rsp+78h+var_18]
0x14001d425  xor     rcx, rsp; StackCookie
0x14001d428  call    __security_check_cookie
0x14001d42d  add     rsp, 70h
0x14001d431  pop     rbx
0x14001d432  retn
0x14001d433  lea     rdx, aIllegalToWaitO; "Illegal to wait on a task in a Windows "...
0x14001d43a  lea     rcx, [rsp+78h+pExceptionObject]; this
0x14001d43f  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x14001d444  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x14001d44b  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x14001d450  call    _CxxThrowException_0
```
