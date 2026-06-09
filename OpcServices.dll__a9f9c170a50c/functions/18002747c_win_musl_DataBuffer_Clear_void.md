# win_musl::DataBuffer::Clear(void)

- ea: `0x18002747c`
- end: `0x1800274ec`
- name: `?Clear@DataBuffer@win_musl@@QEAAXXZ`
- size: `112`
- prototype: `void __fastcall(win_musl::DataBuffer *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18002718c`
- `0x180092a0c`

## callees

- `0x18002747c`
- `0x180028cc0`
- `0x180110ac8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800274bd`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800274bd`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800274d3`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800274d3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800274e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800274e4`

## pseudocode

```c
void __fastcall win_musl::DataBuffer::Clear(win_musl::DataBuffer *this)
{
  HANDLE *v2; // rdi
  const CHAR *v3; // rcx

  std::list<win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>>::clear(this);
  v2 = (HANDLE *)((char *)this + 64);
  if ( (unsigned int)win_scope::scope<void *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::operator int win_scope::detail::dummy_struct::*((char *)this + 64) != -1 )
  {
    if ( SetFilePointerEx(*v2, 0, 0, 0) )
    {
      if ( SetEndOfFile(*v2) )
        goto LABEL_2;
      v3 = "win_musl::DataBuffer::Clear, !truncated is true, failed to truncate file.\n";
    }
    else
    {
      v3 = "win_musl::DataBuffer::Clear, !atZero is true, file not at zero.\n";
    }
    OutputDebugStringA(v3);
  }
LABEL_2:
  *((_QWORD *)this + 9) = 0;
}

```

## disassembly

```asm
0x18002747c  mov     [rsp+arg_0], rbx
0x180027481  push    rdi
0x180027482  sub     rsp, 20h
0x180027486  mov     rbx, rcx
0x180027489  call    ?clear@?$list@V?$scope@PEAUBufferObject@DataBuffer@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAUBufferObject@DataBuffer@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@QEAAXXZ; std::list<win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>>::clear(void)
0x18002748e  lea     rdi, [rbx+40h]
0x180027492  mov     rcx, rdi
0x180027495  call    ??B?$scope@PEAXU?$mutable_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEBAPEQdummy_struct@detail@1@HXZ; win_scope::scope<void *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::operator int win_scope::detail::dummy_struct::*(void)
0x18002749a  cmp     eax, 0FFFFFFFFh
0x18002749d  jnz     short loc_1800274B2
0x18002749f  mov     qword ptr [rbx+48h], 0
0x1800274a7  mov     rbx, [rsp+28h+arg_0]
0x1800274ac  add     rsp, 20h
0x1800274b0  pop     rdi
0x1800274b1  retn
0x1800274b2  mov     rcx, [rdi]; hFile
0x1800274b5  xor     edx, edx; liDistanceToMove
0x1800274b7  xor     r9d, r9d; dwMoveMethod
0x1800274ba  xor     r8d, r8d; lpNewFilePointer
0x1800274bd  call    cs:__imp_SetFilePointerEx
0x1800274c3  test    eax, eax
0x1800274c5  jnz     short loc_1800274D0
0x1800274c7  lea     rcx, aWinMuslDatabuf; "win_musl::DataBuffer::Clear, !atZero is"...
0x1800274ce  jmp     short loc_1800274E4
0x1800274d0  mov     rcx, [rdi]; hFile
0x1800274d3  call    cs:__imp_SetEndOfFile
0x1800274d9  test    eax, eax
0x1800274db  jnz     short loc_18002749F
0x1800274dd  lea     rcx, aWinMuslDatabuf_0; "win_musl::DataBuffer::Clear, !truncated"...
0x1800274e4  call    cs:__imp_OutputDebugStringA
0x1800274ea  jmp     short loc_18002749F
```
