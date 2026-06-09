# CCoSimpleArray<Microsoft::WRL::ComPtr<MitigationServiceResult>,4294967294,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<MitigationServiceResult>>>::~CCoSimpleArray<Microsoft::WRL::ComPtr<MitigationServiceResult>,4294967294,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<MitigationServiceResult>>>(void)

- ea: `0x180019b50`
- end: `0x180019bb6`
- name: `??1?$CCoSimpleArray@V?$ComPtr@VMitigationServiceResult@@@WRL@Microsoft@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@VMitigationServiceResult@@@WRL@Microsoft@@@@@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(__int64)`
- caller_count: `10`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019b44`
- `0x18001bfd0`
- `0x18001c700`
- `0x18001c7b0`
- `0x18001cbfc`
- `0x18001d75c`
- `0x18001f7ec`
- `0x180020b20`
- `0x1800557c8`
- `0x180058000`

## callees

- `0x18001055c`
- `0x180019b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b8a`

## pseudocode

```c
void __fastcall CCoSimpleArray<Microsoft::WRL::ComPtr<MitigationServiceResult>,4294967294,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<MitigationServiceResult>>>::~CCoSimpleArray<Microsoft::WRL::ComPtr<MitigationServiceResult>,4294967294,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<MitigationServiceResult>>>(
        __int64 a1)
{
  unsigned __int64 *v1; // rdi
  unsigned __int64 i; // rsi

  v1 = (unsigned __int64 *)(a1 + 8);
  if ( *(_QWORD *)a1 )
  {
    for ( i = 0; i < *v1; ++i )
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(*(_QWORD *)a1 + 8 * i);
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 24) = 0;
  *v1 = 0;
}

```

## disassembly

```asm
0x180019b50  mov     [rsp+arg_0], rbx
0x180019b55  mov     [rsp+arg_8], rsi
0x180019b5a  push    rdi
0x180019b5b  sub     rsp, 20h
0x180019b5f  cmp     qword ptr [rcx], 0
0x180019b63  lea     rdi, [rcx+8]
0x180019b67  mov     rbx, rcx
0x180019b6a  jz      short loc_180019B97
0x180019b6c  xor     esi, esi
0x180019b6e  cmp     [rdi], rsi
0x180019b71  jbe     short loc_180019B87
0x180019b73  mov     rax, [rbx]
0x180019b76  lea     rcx, [rax+rsi*8]
0x180019b7a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180019b7f  inc     rsi
0x180019b82  cmp     rsi, [rdi]
0x180019b85  jb      short loc_180019B73
0x180019b87  mov     rcx, [rbx]; pv
0x180019b8a  call    cs:__imp_CoTaskMemFree
0x180019b90  mov     qword ptr [rbx], 0
0x180019b97  mov     rsi, [rsp+28h+arg_8]
0x180019b9c  mov     qword ptr [rbx+18h], 0
0x180019ba4  mov     rbx, [rsp+28h+arg_0]
0x180019ba9  mov     qword ptr [rdi], 0
0x180019bb0  add     rsp, 20h
0x180019bb4  pop     rdi
0x180019bb5  retn
```
