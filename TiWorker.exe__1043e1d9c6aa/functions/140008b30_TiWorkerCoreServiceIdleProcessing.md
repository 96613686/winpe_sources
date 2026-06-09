# TiWorkerCoreServiceIdleProcessing

- ea: `0x140008b30`
- end: `0x140008bd1`
- name: `TiWorkerCoreServiceIdleProcessing`
- size: `161`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14000b174`

## callees

- `0x140002310`
- `0x140008b30`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x140008b64`: `No complete result specified`
- `0x140008b98`: `Warning: Failed while executing service idle processing.`

## pseudocode

```c
__int64 __fastcall TiWorkerCoreServiceIdleProcessing(_DWORD *a1)
{
  unsigned int v2; // ebx
  int v3; // eax
  int v5; // [rsp+20h] [rbp-18h] BYREF

  v5 = 1;
  if ( a1 )
  {
    v2 = 0;
    if ( vpfnCbsCoreServiceIdleProcessing )
    {
      v3 = vpfnCbsCoreServiceIdleProcessing(1, &v5);
      v2 = v3;
      if ( v3 < 0 )
        CBSWdsLog(0x4000000, (unsigned int)v3, 1, "Warning: Failed while executing service idle processing.");
    }
    *a1 = v5;
  }
  else
  {
    v2 = -2147467261;
    CBSWdsLog(0x4000000, 2147500035LL, 1, "No complete result specified");
  }
  return v2;
}

```

## disassembly

```asm
0x140008b30  mov     [rsp+arg_8], rbx
0x140008b35  push    rdi
0x140008b36  sub     rsp, 30h
0x140008b3a  mov     rax, cs:__security_cookie
0x140008b41  xor     rax, rsp
0x140008b44  mov     [rsp+38h+var_10], rax
0x140008b49  mov     [rsp+38h+var_18], 1
0x140008b51  mov     rdi, rcx
0x140008b54  test    rcx, rcx
0x140008b57  jnz     short loc_140008B77
0x140008b59  lea     r8d, [rcx+1]
0x140008b5d  mov     ebx, 80004003h
0x140008b62  mov     edx, ebx
0x140008b64  lea     r9, aNoCompleteResu; "No complete result specified"
0x140008b6b  mov     ecx, 4000000h
0x140008b70  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008b75  jmp     short loc_140008BB7
0x140008b77  mov     rax, cs:?vpfnCbsCoreServiceIdleProcessing@@3P6AJHPEAH@ZEA; long (*vpfnCbsCoreServiceIdleProcessing)(int,int *)
0x140008b7e  xor     ebx, ebx
0x140008b80  test    rax, rax
0x140008b83  jz      short loc_140008BB1
0x140008b85  lea     rdx, [rsp+38h+var_18]
0x140008b8a  lea     ecx, [rbx+1]
0x140008b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008b92  mov     ebx, eax
0x140008b94  test    eax, eax
0x140008b96  jns     short loc_140008BB1
0x140008b98  lea     r9, aWarningFailedW; "Warning: Failed while executing service"...
0x140008b9f  mov     r8d, 1
0x140008ba5  mov     edx, eax
0x140008ba7  mov     ecx, 4000000h
0x140008bac  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008bb1  mov     ecx, [rsp+38h+var_18]
0x140008bb5  mov     [rdi], ecx
0x140008bb7  mov     eax, ebx
0x140008bb9  mov     rcx, [rsp+38h+var_10]
0x140008bbe  xor     rcx, rsp; StackCookie
0x140008bc1  call    __security_check_cookie
0x140008bc6  mov     rbx, [rsp+38h+arg_8]
0x140008bcb  add     rsp, 30h
0x140008bcf  pop     rdi
0x140008bd0  retn
```
