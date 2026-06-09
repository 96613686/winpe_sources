# _hypothesis_builder::DetachInPlace(tagHYPOTHESIS &,ulong *,ulong *)

- ea: `0x1800078ac`
- end: `0x180007951`
- name: `?DetachInPlace@_hypothesis_builder@@IEAAJAEAUtagHYPOTHESIS@@PEAK1@Z`
- size: `165`
- prototype: `__int64 __fastcall(WCHAR **this, struct tagHYPOTHESIS *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007714`

## callees

- `0x1800078ac`
- `0x180007958`
- `0x18000c168`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078ed`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::DetachInPlace(
        WCHAR **this,
        struct tagHYPOTHESIS *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  _OWORD *v8; // rcx
  WCHAR *v9; // rax
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  pv = 0;
  _hypothesis_builder::DoDetach((_hypothesis_builder *)this, (struct tagHYPOTHESIS **)&pv);
  v8 = pv;
  if ( pv )
  {
    *(_OWORD *)&a2->pwszClassName = *(_OWORD *)pv;
    *(_OWORD *)&a2->celt = v8[1];
    CoTaskMemFree(v8);
  }
  else
  {
    if ( *((_DWORD *)this + 4) || this[3] )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    a2->pwszClassName = *this;
    v9 = this[1];
    *this = 0;
    a2->pwszDescription = v9;
    this[1] = 0;
    a2->celt = 0;
    a2->rgAttributes = 0;
  }
  *a3 = 1;
  if ( a4 )
    *a4 = 32;
  return 0;
}

```

## disassembly

```asm
0x1800078ac  push    rbx
0x1800078ae  push    rsi
0x1800078af  push    rdi
0x1800078b0  push    r14
0x1800078b2  sub     rsp, 28h
0x1800078b6  mov     rdi, rdx
0x1800078b9  mov     [rsp+48h+pv], 0
0x1800078c2  lea     rdx, [rsp+48h+pv]; struct tagHYPOTHESIS **
0x1800078c7  mov     rsi, r9
0x1800078ca  mov     r14, r8
0x1800078cd  mov     rbx, rcx
0x1800078d0  call    ?DoDetach@_hypothesis_builder@@IEAAXPEAPEAUtagHYPOTHESIS@@@Z; _hypothesis_builder::DoDetach(tagHYPOTHESIS * *)
0x1800078d5  mov     rcx, [rsp+48h+pv]; pv
0x1800078da  test    rcx, rcx
0x1800078dd  jz      short loc_1800078F5
0x1800078df  movups  xmm0, xmmword ptr [rcx]
0x1800078e2  movups  xmmword ptr [rdi], xmm0
0x1800078e5  movups  xmm1, xmmword ptr [rcx+10h]
0x1800078e9  movups  xmmword ptr [rdi+10h], xmm1
0x1800078ed  call    cs:__imp_CoTaskMemFree
0x1800078f3  jmp     short loc_180007933
0x1800078f5  cmp     dword ptr [rbx+10h], 0
0x1800078f9  jnz     short loc_180007902
0x1800078fb  cmp     qword ptr [rbx+18h], 0
0x180007900  jz      short loc_180007907
0x180007902  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007907  mov     rax, [rbx]
0x18000790a  mov     [rdi], rax
0x18000790d  mov     rax, [rbx+8]
0x180007911  mov     qword ptr [rbx], 0
0x180007918  mov     [rdi+8], rax
0x18000791c  mov     qword ptr [rbx+8], 0
0x180007924  mov     dword ptr [rdi+10h], 0
0x18000792b  mov     qword ptr [rdi+18h], 0
0x180007933  mov     dword ptr [r14], 1
0x18000793a  test    rsi, rsi
0x18000793d  jz      short loc_180007945
0x18000793f  mov     dword ptr [rsi], 20h ; ' '
0x180007945  xor     eax, eax
0x180007947  add     rsp, 28h
0x18000794b  pop     r14
0x18000794d  pop     rdi
0x18000794e  pop     rsi
0x18000794f  pop     rbx
0x180007950  retn
```
