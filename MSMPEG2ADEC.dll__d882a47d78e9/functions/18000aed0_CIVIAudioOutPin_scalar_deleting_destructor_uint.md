# CIVIAudioOutPin::`scalar deleting destructor'(uint)

- ea: `0x18000aed0`
- end: `0x18000afce`
- name: `??_GCIVIAudioOutPin@@UEAAPEAXI@Z`
- size: `254`
- prototype: `void *__fastcall(CIVIAudioOutPin *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800013a0`
- `0x180001b80`
- `0x18000aed0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af80`

## pseudocode

```c
CIVIAudioOutPin *__fastcall CIVIAudioOutPin::`scalar deleting destructor'(CIVIAudioOutPin *this, char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)this = &CIVIAudioOutPin::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CIVIAudioOutPin::`vftable'{for `IPin'};
  *((_QWORD *)this + 4) = &CTransformOutputPin::`vftable'{for `IQualityControl'};
  v4 = *((_QWORD *)this + 31);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v4 + 16) + 24LL))(v4 + 16, 1);
    *((_QWORD *)this + 31) = 0;
  }
  *(_QWORD *)this = &CTransformOutputPin::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CIVIAudioOutPin::`vftable'{for `IPin'};
  *((_QWORD *)this + 4) = &CTransformOutputPin::`vftable'{for `IQualityControl'};
  v5 = *((_QWORD *)this + 30);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  operator delete(*((void **)this + 5));
  if ( *((_DWORD *)this + 44) )
  {
    CoTaskMemFree(*((LPVOID *)this + 23));
    *((_DWORD *)this + 44) = 0;
    *((_QWORD *)this + 23) = 0;
  }
  *((_QWORD *)this + 21) = 0;
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000aed0  mov     [rsp+arg_0], rbx
0x18000aed5  mov     [rsp+arg_8], rsi
0x18000aeda  push    rdi
0x18000aedb  sub     rsp, 20h
0x18000aedf  mov     edi, edx
0x18000aee1  mov     rbx, rcx
0x18000aee4  lea     rax, ??_7CIVIAudioOutPin@@6BCUnknown@@@; const CIVIAudioOutPin::`vftable'{for `CUnknown'}
0x18000aeeb  mov     [rcx], rax
0x18000aeee  lea     rax, ??_7CIVIAudioOutPin@@6BIPin@@@; const CIVIAudioOutPin::`vftable'{for `IPin'}
0x18000aef5  mov     [rcx+18h], rax
0x18000aef9  lea     rax, ??_7CTransformOutputPin@@6BIQualityControl@@@; const CTransformOutputPin::`vftable'{for `IQualityControl'}
0x18000af00  mov     [rcx+20h], rax
0x18000af04  mov     rcx, [rcx+0F8h]
0x18000af0b  xor     esi, esi
0x18000af0d  test    rcx, rcx
0x18000af10  jz      short loc_18000AF2F
0x18000af12  add     rcx, 10h
0x18000af16  mov     rax, [rcx]
0x18000af19  mov     edx, 1
0x18000af1e  mov     rax, [rax+18h]
0x18000af22  call    cs:__guard_dispatch_icall_fptr
0x18000af28  mov     [rbx+0F8h], rsi
0x18000af2f  lea     rax, ??_7CTransformOutputPin@@6BCUnknown@@@; const CTransformOutputPin::`vftable'{for `CUnknown'}
0x18000af36  mov     [rbx], rax
0x18000af39  lea     rax, ??_7CIVIAudioOutPin@@6BIPin@@@; const CIVIAudioOutPin::`vftable'{for `IPin'}
0x18000af40  mov     [rbx+18h], rax
0x18000af44  lea     rax, ??_7CTransformOutputPin@@6BIQualityControl@@@; const CTransformOutputPin::`vftable'{for `IQualityControl'}
0x18000af4b  mov     [rbx+20h], rax
0x18000af4f  mov     rcx, [rbx+0F0h]
0x18000af56  test    rcx, rcx
0x18000af59  jz      short loc_18000AF68
0x18000af5b  mov     rax, [rcx]
0x18000af5e  mov     rax, [rax+10h]
0x18000af62  call    cs:__guard_dispatch_icall_fptr
0x18000af68  mov     rcx, [rbx+28h]; Block
0x18000af6c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000af71  cmp     [rbx+0B0h], esi
0x18000af77  jz      short loc_18000AF99
0x18000af79  mov     rcx, [rbx+0B8h]; pv
0x18000af80  call    cs:__imp_CoTaskMemFree
0x18000af87  nop     dword ptr [rax+rax+00h]
0x18000af8c  mov     [rbx+0B0h], esi
0x18000af92  mov     [rbx+0B8h], rsi
0x18000af99  mov     [rbx+0A8h], rsi
0x18000afa0  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18000afa7  test    dil, 1
0x18000afab  jz      short loc_18000AFBA
0x18000afad  mov     edx, 108h
0x18000afb2  mov     rcx, rbx; Block
0x18000afb5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000afba  mov     rax, rbx
0x18000afbd  mov     rbx, [rsp+28h+arg_0]
0x18000afc2  mov     rsi, [rsp+28h+arg_8]
0x18000afc7  add     rsp, 20h
0x18000afcb  pop     rdi
0x18000afcc  retn
```
