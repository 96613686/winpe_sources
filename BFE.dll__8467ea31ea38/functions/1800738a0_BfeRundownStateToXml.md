# BfeRundownStateToXml

- ea: `0x1800738a0`
- end: `0x18007399a`
- name: `BfeRundownStateToXml`
- size: `250`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800736f0`
- `0x1800739a0`

## callees

- `0x18000e000`
- `0x18001236c`
- `0x180018b74`
- `0x18001d91c`
- `0x180030abc`
- `0x1800738a0`
- `0x18007d9ec`
- `0x18007db60`
- `0x180087854`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007393a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007393a`

## string_xrefs

- `0x1800738cb`: `BfeRundownStateToXml`
- `0x18007397d`: `BfeRundownStateToXml`
- `0x18007394d`: `FwppFileWriterClose`

## pseudocode

```c
__int64 __fastcall BfeRundownStateToXml(const WCHAR *a1)
{
  __int64 v1; // rbx
  __int64 v2; // rdx
  __int64 v3; // rax
  __int64 v4; // rdi
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF
  __int64 v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = 0;
  v8 = 0;
  if ( byte_1800F2749 )
  {
    v1 = BfeExpandEnvironmentStrings(a1);
    if ( !v1 )
    {
      v3 = FwppXmlFileWriterCreate(v8, v2, &v9);
      v4 = v9;
      v1 = v3;
      if ( !v3 )
        v1 = FwppTlgWriteCurrentState(v9);
      if ( v4 )
      {
        v5 = *(_QWORD *)(v4 + 8);
        if ( v5 )
        {
          v6 = FwppFileWriterFlush(v5);
          if ( v6 )
          {
            WfpReportError(v6, "FwppFileWriterClose");
          }
          else
          {
            CloseHandle(*(HANDLE *)(v5 + 65544));
            *(_QWORD *)(v5 + 65544) = -1;
          }
        }
        FwppXmlFileWriterDestroy(&v9);
      }
    }
    if ( v8 )
      WfpMemFree(&v8);
  }
  else
  {
    v1 = WfpReportSysErrorAsWinError(a1, "BfeRundownStateToXml", 21);
  }
  if ( v1 )
    WfpReportError(v1, "BfeRundownStateToXml");
  return v1;
}

```

## disassembly

```asm
0x1800738a0  mov     [rsp+arg_0], rbx
0x1800738a5  push    rdi
0x1800738a6  sub     rsp, 20h
0x1800738aa  cmp     cs:byte_1800F2749, 0
0x1800738b1  mov     [rsp+28h+arg_10], 0
0x1800738ba  mov     [rsp+28h+arg_8], 0
0x1800738c3  jnz     short loc_1800738DF
0x1800738c5  mov     r8d, 15h
0x1800738cb  lea     rdx, aBferundownstat_0; "BfeRundownStateToXml"
0x1800738d2  call    WfpReportSysErrorAsWinError
0x1800738d7  mov     rbx, rax
0x1800738da  jmp     loc_180073978
0x1800738df  lea     rdx, [rsp+28h+arg_8]
0x1800738e4  call    BfeExpandEnvironmentStrings
0x1800738e9  mov     rbx, rax
0x1800738ec  test    rax, rax
0x1800738ef  jnz     short loc_180073966
0x1800738f1  mov     rcx, [rsp+28h+arg_8]
0x1800738f6  lea     r8, [rsp+28h+arg_10]
0x1800738fb  call    FwppXmlFileWriterCreate
0x180073900  mov     rdi, [rsp+28h+arg_10]
0x180073905  mov     rbx, rax
0x180073908  test    rax, rax
0x18007390b  jnz     short loc_180073918
0x18007390d  mov     rcx, rdi
0x180073910  call    FwppTlgWriteCurrentState
0x180073915  mov     rbx, rax
0x180073918  test    rdi, rdi
0x18007391b  jz      short loc_180073966
0x18007391d  mov     rdi, [rdi+8]
0x180073921  test    rdi, rdi
0x180073924  jz      short loc_18007395C
0x180073926  mov     rcx, rdi
0x180073929  call    FwppFileWriterFlush
0x18007392e  test    rax, rax
0x180073931  jnz     short loc_18007394D
0x180073933  mov     rcx, [rdi+10008h]; hObject
0x18007393a  call    cs:__imp_CloseHandle
0x180073940  mov     qword ptr [rdi+10008h], 0FFFFFFFFFFFFFFFFh
0x18007394b  jmp     short loc_18007395C
0x18007394d  lea     rdx, aFwppfilewriter; "FwppFileWriterClose"
0x180073954  mov     rcx, rax
0x180073957  call    WfpReportError
0x18007395c  lea     rcx, [rsp+28h+arg_10]
0x180073961  call    FwppXmlFileWriterDestroy
0x180073966  cmp     [rsp+28h+arg_8], 0
0x18007396c  jz      short loc_180073978
0x18007396e  lea     rcx, [rsp+28h+arg_8]
0x180073973  call    WfpMemFree
0x180073978  test    rbx, rbx
0x18007397b  jz      short loc_18007398C
0x18007397d  lea     rdx, aBferundownstat_0; "BfeRundownStateToXml"
0x180073984  mov     rcx, rbx
0x180073987  call    WfpReportError
0x18007398c  mov     rax, rbx
0x18007398f  mov     rbx, [rsp+28h+arg_0]
0x180073994  add     rsp, 20h
0x180073998  pop     rdi
0x180073999  retn
```
