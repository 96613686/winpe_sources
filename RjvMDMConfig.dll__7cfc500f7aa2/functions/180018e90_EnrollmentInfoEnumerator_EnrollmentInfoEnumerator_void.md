# EnrollmentInfoEnumerator::~EnrollmentInfoEnumerator(void)

- ea: `0x180018e90`
- end: `0x180018f1a`
- name: `??1EnrollmentInfoEnumerator@@QEAA@XZ`
- size: `138`
- prototype: `void __fastcall(EnrollmentInfoEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019620`

## callees

- `0x180018e90`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180018ed2`
- `OLEAUT32!__imp_SysFreeString` at `0x180018ed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ef5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ef5`

## pseudocode

```c
void __fastcall EnrollmentInfoEnumerator::~EnrollmentInfoEnumerator(EnrollmentInfoEnumerator *this)
{
  __int64 i; // rdi
  OLECHAR *v3; // rcx

  *(_QWORD *)this = &EnrollmentInfoEnumerator::`vftable'{for `IEnrollmentInfoEnumerator'};
  *((_QWORD *)this + 1) = &EnrollmentInfoEnumerator::`vftable'{for `IAttachEnrollEngine'};
  if ( *((_QWORD *)this + 6) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 10); i = (unsigned int)(i + 1) )
    {
      v3 = *(OLECHAR **)(*((_QWORD *)this + 6) + 8 * i);
      if ( v3 )
      {
        SysFreeString(v3);
        *(_QWORD *)(*((_QWORD *)this + 6) + 8 * i) = 0;
      }
    }
    CoTaskMemFree(*((LPVOID *)this + 6));
    *((_QWORD *)this + 6) = 0;
  }
}

```

## disassembly

```asm
0x180018e90  mov     [rsp+arg_0], rbx
0x180018e95  mov     [rsp+arg_8], rsi
0x180018e9a  push    rdi
0x180018e9b  sub     rsp, 20h
0x180018e9f  mov     rbx, rcx
0x180018ea2  lea     rax, ??_7EnrollmentInfoEnumerator@@6BIEnrollmentInfoEnumerator@@@; const EnrollmentInfoEnumerator::`vftable'{for `IEnrollmentInfoEnumerator'}
0x180018ea9  mov     [rcx], rax
0x180018eac  lea     rax, ??_7EnrollmentInfoEnumerator@@6BIAttachEnrollEngine@@@; const EnrollmentInfoEnumerator::`vftable'{for `IAttachEnrollEngine'}
0x180018eb3  mov     [rcx+8], rax
0x180018eb7  cmp     qword ptr [rcx+30h], 0
0x180018ebc  jz      short loc_180018F09
0x180018ebe  xor     edi, edi
0x180018ec0  cmp     [rcx+28h], edi
0x180018ec3  jbe     short loc_180018EF1
0x180018ec5  mov     rax, [rbx+30h]
0x180018ec9  mov     rcx, [rax+rdi*8]; bstrString
0x180018ecd  test    rcx, rcx
0x180018ed0  jz      short loc_180018EEA
0x180018ed2  call    cs:__imp_SysFreeString
0x180018ed9  nop     dword ptr [rax+rax+00h]
0x180018ede  mov     rax, [rbx+30h]
0x180018ee2  mov     qword ptr [rax+rdi*8], 0
0x180018eea  inc     edi
0x180018eec  cmp     edi, [rbx+28h]
0x180018eef  jb      short loc_180018EC5
0x180018ef1  mov     rcx, [rbx+30h]; pv
0x180018ef5  call    cs:__imp_CoTaskMemFree
0x180018efc  nop     dword ptr [rax+rax+00h]
0x180018f01  mov     qword ptr [rbx+30h], 0
0x180018f09  mov     rbx, [rsp+28h+arg_0]
0x180018f0e  mov     rsi, [rsp+28h+arg_8]
0x180018f13  add     rsp, 20h
0x180018f17  pop     rdi
0x180018f18  retn
```
