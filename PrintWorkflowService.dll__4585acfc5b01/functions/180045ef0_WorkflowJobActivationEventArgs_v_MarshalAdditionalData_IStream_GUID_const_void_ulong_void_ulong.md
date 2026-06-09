# WorkflowJobActivationEventArgs::v_MarshalAdditionalData(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x180045ef0`
- end: `0x180045f75`
- name: `?v_MarshalAdditionalData@WorkflowJobActivationEventArgs@@EEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `133`
- prototype: `int(WorkflowJobActivationEventArgs *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800127a4`
- `0x180045ef0`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180045f0d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180045f29`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180045f0d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180045f29`

## string_xrefs

- `0x180045f4e`: `onecoreuap\printscan\print\workflow\broker\psa_lib\WorkflowJobUIEventsArgs.h`
- `0x180045f62`: `onecoreuap\printscan\print\workflow\broker\psa_lib\WorkflowJobUIEventsArgs.h`

## pseudocode

```c
__int64 __fastcall WorkflowJobActivationEventArgs::v_MarshalAdditionalData(
        WorkflowJobActivationEventArgs *this,
        struct IStream *a2,
        const struct _GUID *a3,
        void *a4)
{
  HRESULT v6; // eax
  HRESULT v7; // eax
  const char *v9; // r9
  __int64 *v10; // rdx
  __int64 v11; // [rsp+0h] [rbp-28h] BYREF
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v14; // [rsp+30h] [rbp+8h]

  v6 = IStream_Write(a2, (char *)this + 80, 4u);
  if ( v6 < 0 )
  {
    try
    {
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\WorkflowJobUIEventsArgs.h",
        (const char *)(unsigned int)v6,
        v12);
    }
    catch ( ... )
    {
      v10 = &v11;
      *((_DWORD *)v10 + 12) = wil::details::in1diag3::Return_CaughtException(
                                (wil::details::in1diag3 *)v10[5],
                                (void *)0x18,
                                (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\WorkflowJobUIEventsArgs.h",
                                v9);
      return v14;
    }
  }
  v7 = IStream_Write(a2, (char *)this - 24, 4u);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\WorkflowJobUIEventsArgs.h",
      (const char *)(unsigned int)v7,
      v12);
  return 0;
}

```

## disassembly

```asm
0x180045ef0  mov     [rsp+arg_8], rbx
0x180045ef5  push    rdi; int
0x180045ef6  sub     rsp, 20h
0x180045efa  mov     rbx, rdx
0x180045efd  mov     rdi, rcx
0x180045f00  lea     rdx, [rcx+50h]; pv
0x180045f04  mov     r8d, 4; cb
0x180045f0a  mov     rcx, rbx; pstm
0x180045f0d  call    cs:__imp_IStream_Write
0x180045f13  mov     rcx, [rsp+28h]; this
0x180045f18  test    eax, eax
0x180045f1a  js      short loc_180045F4B
0x180045f1c  lea     rdx, [rdi-18h]; pv
0x180045f20  mov     r8d, 4; cb
0x180045f26  mov     rcx, rbx; pstm
0x180045f29  call    cs:__imp_IStream_Write
0x180045f2f  mov     rcx, [rsp+28h]; this
0x180045f34  test    eax, eax
0x180045f36  js      short loc_180045F5F
0x180045f38  xor     eax, eax
0x180045f3a  jmp     short loc_180045F40
0x180045f3c  mov     eax, [rsp+28h+arg_0]
0x180045f40  mov     rbx, [rsp+28h+arg_8]
0x180045f45  add     rsp, 20h
0x180045f49  pop     rdi
0x180045f4a  retn
0x180045f4b  mov     r9d, eax; char *
0x180045f4e  lea     r8, aOnecoreuapPrin_17; "onecoreuap\\printscan\\print\\workflow"...
0x180045f55  mov     edx, 14h; void *
0x180045f5a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045f5f  mov     r9d, eax; char *
0x180045f62  lea     r8, aOnecoreuapPrin_17; "onecoreuap\\printscan\\print\\workflow"...
0x180045f69  mov     edx, 15h; void *
0x180045f6e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
