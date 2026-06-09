# BfeRundownStateToXml

- ea: `0x180076284`
- end: `0x180076385`
- name: `BfeRundownStateToXml`
- size: `257`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800760b0`
- `0x180076390`

## callees

- `0x18000e7e0`
- `0x180012d8c`
- `0x1800197d0`
- `0x18003b1ac`
- `0x180044588`
- `0x180076284`
- `0x180080834`
- `0x1800809ac`
- `0x18008a794`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007631e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007631e`

## string_xrefs

- `0x1800762af`: `BfeRundownStateToXml`
- `0x180076367`: `BfeRundownStateToXml`
- `0x180076337`: `FwppFileWriterClose`

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
  if ( byte_1800F5769 )
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
0x180076284  mov     [rsp+arg_0], rbx
0x180076289  push    rdi
0x18007628a  sub     rsp, 20h
0x18007628e  cmp     cs:byte_1800F5769, 0
0x180076295  mov     [rsp+28h+arg_10], 0
0x18007629e  mov     [rsp+28h+arg_8], 0
0x1800762a7  jnz     short loc_1800762C3
0x1800762a9  mov     r8d, 15h
0x1800762af  lea     rdx, aBferundownstat_0; "BfeRundownStateToXml"
0x1800762b6  call    WfpReportSysErrorAsWinError
0x1800762bb  mov     rbx, rax
0x1800762be  jmp     loc_180076362
0x1800762c3  lea     rdx, [rsp+28h+arg_8]
0x1800762c8  call    BfeExpandEnvironmentStrings
0x1800762cd  mov     rbx, rax
0x1800762d0  test    rax, rax
0x1800762d3  jnz     short loc_180076350
0x1800762d5  mov     rcx, [rsp+28h+arg_8]
0x1800762da  lea     r8, [rsp+28h+arg_10]
0x1800762df  call    FwppXmlFileWriterCreate
0x1800762e4  mov     rdi, [rsp+28h+arg_10]
0x1800762e9  mov     rbx, rax
0x1800762ec  test    rax, rax
0x1800762ef  jnz     short loc_1800762FC
0x1800762f1  mov     rcx, rdi
0x1800762f4  call    FwppTlgWriteCurrentState
0x1800762f9  mov     rbx, rax
0x1800762fc  test    rdi, rdi
0x1800762ff  jz      short loc_180076350
0x180076301  mov     rdi, [rdi+8]
0x180076305  test    rdi, rdi
0x180076308  jz      short loc_180076346
0x18007630a  mov     rcx, rdi
0x18007630d  call    FwppFileWriterFlush
0x180076312  test    rax, rax
0x180076315  jnz     short loc_180076337
0x180076317  mov     rcx, [rdi+10008h]; hObject
0x18007631e  call    cs:__imp_CloseHandle
0x180076325  nop     dword ptr [rax+rax+00h]
0x18007632a  mov     qword ptr [rdi+10008h], 0FFFFFFFFFFFFFFFFh
0x180076335  jmp     short loc_180076346
0x180076337  lea     rdx, aFwppfilewriter; "FwppFileWriterClose"
0x18007633e  mov     rcx, rax
0x180076341  call    WfpReportError
0x180076346  lea     rcx, [rsp+28h+arg_10]
0x18007634b  call    FwppXmlFileWriterDestroy
0x180076350  cmp     [rsp+28h+arg_8], 0
0x180076356  jz      short loc_180076362
0x180076358  lea     rcx, [rsp+28h+arg_8]
0x18007635d  call    WfpMemFree
0x180076362  test    rbx, rbx
0x180076365  jz      short loc_180076376
0x180076367  lea     rdx, aBferundownstat_0; "BfeRundownStateToXml"
0x18007636e  mov     rcx, rbx
0x180076371  call    WfpReportError
0x180076376  mov     rax, rbx
0x180076379  mov     rbx, [rsp+28h+arg_0]
0x18007637e  add     rsp, 20h
0x180076382  pop     rdi
0x180076383  retn
```
