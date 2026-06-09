# TokenListToGuidArray(ushort *,ushort,_GUID * *,uint *)

- ea: `0x180030c50`
- end: `0x180030d4b`
- name: `?TokenListToGuidArray@@YAJPEAGGPEAPEAU_GUID@@PEAI@Z`
- size: `251`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, struct _GUID **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180030dd4`

## callees

- `0x180002470`
- `0x18000247c`
- `0x180002494`
- `0x180030c50`
- `0x180030d54`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180030ce2`
- `ntdll!RtlInitUnicodeString` at `0x180030ce2`
- `ntdll!RtlGUIDFromString` at `0x180030cf5`
- `ntdll!RtlGUIDFromString` at `0x180030cf5`

## pseudocode

```c
__int64 __fastcall TokenListToGuidArray(unsigned __int16 *a1, __int64 a2, struct _GUID **a3, unsigned int *a4)
{
  NTSTATUS v7; // edi
  size_t v8; // r14
  struct _GUID *v9; // rax
  wchar_t *i; // rcx
  wchar_t *v11; // rax
  wchar_t Delimiter; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-18h] BYREF
  unsigned int v15; // [rsp+78h] [rbp+38h] BYREF
  wchar_t *Context; // [rsp+80h] [rbp+40h] BYREF

  *a3 = 0;
  *a4 = 0;
  Delimiter = 59;
  Context = 0;
  v15 = 0;
  DestinationString = 0;
  v7 = ValidateTokenArray(a1, 0x3Bu, 0x26u, &v15);
  if ( v7 >= 0 && (v8 = 16LL * v15, v9 = (struct _GUID *)o_malloc_0(v8), (*a3 = v9) != 0) )
  {
    for ( i = a1; ; i = 0 )
    {
      v11 = o_wcstok_s_0(i, &Delimiter, &Context);
      if ( !v11 )
        break;
      if ( 16 * (unsigned __int64)(*a4 + 1) > v8 )
        goto LABEL_9;
      RtlInitUnicodeString(&DestinationString, v11);
      v7 = RtlGUIDFromString(&DestinationString, &(*a3)[*a4]);
      if ( v7 < 0 )
        goto LABEL_9;
      ++*a4;
    }
  }
  else
  {
LABEL_9:
    v7 = -1073741823;
    if ( *a3 )
    {
      free(*a3);
      *a3 = 0;
    }
    *a4 = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180030c50  mov     [rsp-28h+arg_0], rbx
0x180030c55  mov     word ptr [rsp-28h+arg_8], dx
0x180030c5a  push    rbp
0x180030c5b  push    rsi
0x180030c5c  push    rdi
0x180030c5d  push    r14
0x180030c5f  push    r15
0x180030c61  mov     rbp, rsp
0x180030c64  sub     rsp, 40h
0x180030c68  mov     edx, 3Bh ; ';'; unsigned __int16
0x180030c6d  mov     qword ptr [r8], 0
0x180030c74  mov     rsi, r8
0x180030c77  mov     dword ptr [r9], 0
0x180030c7e  mov     rbx, r9
0x180030c81  mov     [rbp+Delimiter], dx
0x180030c85  xorps   xmm0, xmm0
0x180030c88  mov     [rbp+Context], 0
0x180030c90  lea     r8d, [rdx-15h]; unsigned int
0x180030c94  mov     [rbp+arg_8], 0
0x180030c9b  lea     r9, [rbp+arg_8]; unsigned int *
0x180030c9f  mov     r15, rcx
0x180030ca2  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180030ca6  call    ?ValidateTokenArray@@YAJPEAGGIPEAI@Z; ValidateTokenArray(ushort *,ushort,uint,uint *)
0x180030cab  mov     edi, eax
0x180030cad  test    eax, eax
0x180030caf  js      short loc_180030D19
0x180030cb1  mov     r14d, [rbp+arg_8]
0x180030cb5  shl     r14, 4
0x180030cb9  mov     rcx, r14; Size
0x180030cbc  call    _o_malloc_0
0x180030cc1  mov     [rsi], rax
0x180030cc4  test    rax, rax
0x180030cc7  jz      short loc_180030D19
0x180030cc9  mov     rcx, r15
0x180030ccc  jmp     short loc_180030D05
0x180030cce  mov     edx, [rbx]
0x180030cd0  inc     edx
0x180030cd2  shl     rdx, 4
0x180030cd6  cmp     rdx, r14
0x180030cd9  ja      short loc_180030D19
0x180030cdb  mov     rdx, rax; SourceString
0x180030cde  lea     rcx, [rbp+DestinationString]; DestinationString
0x180030ce2  call    cs:__imp_RtlInitUnicodeString
0x180030ce8  mov     edx, [rbx]
0x180030cea  lea     rcx, [rbp+DestinationString]; GuidString
0x180030cee  shl     rdx, 4
0x180030cf2  add     rdx, [rsi]; Guid
0x180030cf5  call    cs:__imp_RtlGUIDFromString
0x180030cfb  mov     edi, eax
0x180030cfd  test    eax, eax
0x180030cff  js      short loc_180030D19
0x180030d01  inc     dword ptr [rbx]
0x180030d03  xor     ecx, ecx; String
0x180030d05  lea     r8, [rbp+Context]; Context
0x180030d09  lea     rdx, [rbp+Delimiter]; Delimiter
0x180030d0d  call    _o_wcstok_s_0
0x180030d12  test    rax, rax
0x180030d15  jnz     short loc_180030CCE
0x180030d17  jmp     short loc_180030D38
0x180030d19  mov     rcx, [rsi]; Block
0x180030d1c  mov     edi, 0C0000001h
0x180030d21  test    rcx, rcx
0x180030d24  jz      short loc_180030D32
0x180030d26  call    free
0x180030d2b  mov     qword ptr [rsi], 0
0x180030d32  mov     dword ptr [rbx], 0
0x180030d38  mov     rbx, [rsp+40h+arg_0]
0x180030d3d  mov     eax, edi
0x180030d3f  add     rsp, 40h
0x180030d43  pop     r15
0x180030d45  pop     r14
0x180030d47  pop     rdi
0x180030d48  pop     rsi
0x180030d49  pop     rbp
0x180030d4a  retn
```
