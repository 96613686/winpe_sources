# UsageAndQualityInsights::Ingestion::MetricDataRecords::~MetricDataRecords(void)

- ea: `0x180019a58`
- end: `0x180019aa7`
- name: `??1MetricDataRecords@Ingestion@UsageAndQualityInsights@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(UsageAndQualityInsights::Ingestion::MetricDataRecords *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019f6c`
- `0x180102d9e`

## callees

- `0x180019a58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019a85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019a96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019a85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019a96`

## pseudocode

```c
void __fastcall UsageAndQualityInsights::Ingestion::MetricDataRecords::~MetricDataRecords(
        UsageAndQualityInsights::Ingestion::MetricDataRecords *this)
{
  __int64 i; // rdi
  void *v3; // rcx

  if ( *((_QWORD *)this + 1) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
    {
      v3 = *(void **)(*((_QWORD *)this + 1) + 24 * i + 16);
      if ( v3 )
        CoTaskMemFree(v3);
    }
    CoTaskMemFree(*((LPVOID *)this + 1));
  }
}

```

## disassembly

```asm
0x180019a58  mov     [rsp+arg_0], rbx
0x180019a5d  push    rdi
0x180019a5e  sub     rsp, 20h
0x180019a62  cmp     qword ptr [rcx+8], 0
0x180019a67  mov     rbx, rcx
0x180019a6a  jz      short loc_180019A9C
0x180019a6c  xor     edi, edi
0x180019a6e  cmp     [rcx+10h], edi
0x180019a71  jbe     short loc_180019A92
0x180019a73  mov     rax, [rbx+8]
0x180019a77  lea     rcx, [rdi+rdi*2]
0x180019a7b  mov     rcx, [rax+rcx*8+10h]; pv
0x180019a80  test    rcx, rcx
0x180019a83  jz      short loc_180019A8B
0x180019a85  call    cs:__imp_CoTaskMemFree
0x180019a8b  inc     edi
0x180019a8d  cmp     edi, [rbx+10h]
0x180019a90  jb      short loc_180019A73
0x180019a92  mov     rcx, [rbx+8]; pv
0x180019a96  call    cs:__imp_CoTaskMemFree
0x180019a9c  mov     rbx, [rsp+28h+arg_0]
0x180019aa1  add     rsp, 20h
0x180019aa5  pop     rdi
0x180019aa6  retn
```
