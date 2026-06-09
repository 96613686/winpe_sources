# Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl::MergeEtlFiles(ushort const *,ushort const * * const,uint,ulong)

- ea: `0x14000f838`
- end: `0x14000f935`
- name: `?MergeEtlFiles@KernelTraceControl@StandardCollector@DiagnosticsHub@Microsoft@@QEAAKPEBGQEAPEBGIK@Z`
- size: `253`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl *this, DiagHubCommon *, DiagHubCommon **, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001388`

## callees

- `0x14000a278`
- `0x14000f484`
- `0x14000f838`
- `0x14000f938`
- `0x140014c70`

## string_xrefs

- `0x14000f87c`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\KernelTraceControl.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl::MergeEtlFiles(
        Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl *this,
        DiagHubCommon *a2,
        DiagHubCommon **a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v5; // rsi
  unsigned int v9; // ebp
  const unsigned __int16 *v10; // rdx
  __int64 FileSizeInBytes; // rax
  __int64 v12; // rax

  v5 = a4;
  v9 = Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl::InitializeKernelTraceControlFunctions(this);
  if ( !v9 )
  {
    DiagHubCommon::LogStream::Write(
      (Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl *)((char *)this + 80),
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\KernelTraceControl.cpp",
      L"Merging ETL files with flags (Flags: 0x%08x)",
      a5);
    v9 = (*((__int64 (__fastcall **)(DiagHubCommon *, DiagHubCommon **, _QWORD, _QWORD))this + 1))(
           a2,
           a3,
           (unsigned int)v5,
           a5);
    if ( !v9 && *((_QWORD *)this + 31) != *((_QWORD *)this + 32) )
    {
      if ( (_DWORD)v5 )
      {
        do
        {
          FileSizeInBytes = DiagHubCommon::GetFileSizeInBytes(*a3, v10);
          DiagHubCommon::LogStream::Write(
            (Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl *)((char *)this + 248),
            L"OriginalEtlFile(Name,ByteSize)",
            L"(%s,%I64d)",
            *a3++,
            FileSizeInBytes);
          --v5;
        }
        while ( v5 );
      }
      v12 = DiagHubCommon::GetFileSizeInBytes(a2, v10);
      DiagHubCommon::LogStream::Write(
        (Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl *)((char *)this + 248),
        L"MergedEtlFile(Name,ByteSize)",
        L"(%s,%I64d)",
        a2,
        v12);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x14000f838  mov     rax, rsp
0x14000f83b  mov     [rax+8], rbx
0x14000f83f  mov     [rax+10h], rbp
0x14000f843  mov     [rax+18h], rsi
0x14000f847  mov     [rax+20h], rdi
0x14000f84b  push    r14
0x14000f84d  sub     rsp, 30h
0x14000f851  mov     esi, r9d
0x14000f854  mov     rdi, r8
0x14000f857  mov     r14, rdx
0x14000f85a  mov     rbx, rcx
0x14000f85d  call    ?InitializeKernelTraceControlFunctions@KernelTraceControl@StandardCollector@DiagnosticsHub@Microsoft@@AEAAKXZ; Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl::InitializeKernelTraceControlFunctions(void)
0x14000f862  mov     ebp, eax
0x14000f864  test    eax, eax
0x14000f866  jnz     loc_14000F918
0x14000f86c  mov     r9d, [rsp+38h+arg_20]
0x14000f871  lea     rcx, [rbx+50h]; this
0x14000f875  lea     r8, aMergingEtlFile; "Merging ETL files with flags (Flags: 0x"...
0x14000f87c  lea     rdx, aDAWork1SSource_2; "D:\\a\\_work\\1\\s\\sources\\Core\\Diag"...
0x14000f883  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x14000f888  mov     r9d, [rsp+38h+arg_20]
0x14000f88d  mov     r8d, esi
0x14000f890  mov     rax, [rbx+8]
0x14000f894  mov     rdx, rdi
0x14000f897  mov     rcx, r14
0x14000f89a  call    cs:__guard_dispatch_icall_fptr
0x14000f8a0  mov     ebp, eax
0x14000f8a2  test    eax, eax
0x14000f8a4  jnz     short loc_14000F918
0x14000f8a6  mov     rax, [rbx+100h]
0x14000f8ad  cmp     [rbx+0F8h], rax
0x14000f8b4  jz      short loc_14000F918
0x14000f8b6  test    esi, esi
0x14000f8b8  jz      short loc_14000F8EE
0x14000f8ba  mov     rcx, [rdi]; this
0x14000f8bd  call    ?GetFileSizeInBytes@DiagHubCommon@@YA_JPEBG@Z; DiagHubCommon::GetFileSizeInBytes(ushort const *)
0x14000f8c2  mov     r9, [rdi]
0x14000f8c5  lea     r8, aSI64d; "(%s,%I64d)"
0x14000f8cc  lea     rdx, aOriginaletlfil; "OriginalEtlFile(Name,ByteSize)"
0x14000f8d3  mov     [rsp+38h+var_18], rax
0x14000f8d8  lea     rcx, [rbx+0F8h]; this
0x14000f8df  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x14000f8e4  lea     rdi, [rdi+8]
0x14000f8e8  sub     rsi, 1
0x14000f8ec  jnz     short loc_14000F8BA
0x14000f8ee  mov     rcx, r14; this
0x14000f8f1  call    ?GetFileSizeInBytes@DiagHubCommon@@YA_JPEBG@Z; DiagHubCommon::GetFileSizeInBytes(ushort const *)
0x14000f8f6  mov     r9, r14
0x14000f8f9  mov     [rsp+38h+var_18], rax
0x14000f8fe  lea     r8, aSI64d; "(%s,%I64d)"
0x14000f905  lea     rdx, aMergedetlfileN; "MergedEtlFile(Name,ByteSize)"
0x14000f90c  lea     rcx, [rbx+0F8h]; this
0x14000f913  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x14000f918  mov     rbx, [rsp+38h+arg_0]
0x14000f91d  mov     eax, ebp
0x14000f91f  mov     rbp, [rsp+38h+arg_8]
0x14000f924  mov     rsi, [rsp+38h+arg_10]
0x14000f929  mov     rdi, [rsp+38h+arg_18]
0x14000f92e  add     rsp, 30h
0x14000f932  pop     r14
0x14000f934  retn
```
