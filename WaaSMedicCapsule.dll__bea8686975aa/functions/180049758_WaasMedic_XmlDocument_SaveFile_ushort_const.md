# WaasMedic::XmlDocument::SaveFile(ushort const *)

- ea: `0x180049758`
- end: `0x180049921`
- name: `?SaveFile@XmlDocument@WaasMedic@@QEAAJPEBG@Z`
- size: `457`
- prototype: `int(WaasMedic::XmlDocument *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18004815c`

## callees

- `0x18002543c`
- `0x180049758`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800497d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004982c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800498c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800497d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004982c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800498c4`
- `OLEAUT32!__imp_SysAllocString` at `0x18004976e`
- `OLEAUT32!__imp_SysAllocString` at `0x180049786`
- `OLEAUT32!__imp_SysAllocString` at `0x18004976e`
- `OLEAUT32!__imp_SysAllocString` at `0x180049786`
- `OLEAUT32!__imp_SysFreeString` at `0x1800497ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18004990c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800497ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18004990c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800497c4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800497c4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180049822`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800498ba`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180049822`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800498ba`

## string_xrefs

- `0x18004979c`: `Failed to allocate path`
- `0x180049809`: `Remove readonly attribute from [%s] for writing`
- `0x1800497f5`: `Xml file [%s] is readonly`
- `0x1800498a1`: `Restore readonly attribute to [%s] afterwriting`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::XmlDocument::SaveFile(WaasMedic::XmlDocument *this, const unsigned __int16 *a2)
{
  const OLECHAR *v4; // rax
  OLECHAR *v5; // rbx
  char v7; // r14
  DWORD FileAttributesW; // esi
  signed int LastError; // eax
  signed int v10; // eax
  __int64 v11; // rcx
  int v12; // ebp
  signed int v13; // eax
  _QWORD v14[11]; // [rsp+20h] [rbp-58h] BYREF

  v4 = SysAllocString(a2);
  v5 = 0;
  if ( v4 )
    v5 = SysAllocString(v4);
  if ( v5 )
  {
    v7 = 0;
    FileAttributesW = GetFileAttributesW(a2);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LogLevelW(3u, L"Failed to get file attributes for [%s]. Err=0x%08x", a2, (unsigned int)LastError);
    }
    else if ( (FileAttributesW & 1) != 0 )
    {
      LogLevelW(4u, L"Xml file [%s] is readonly", a2);
      LogLevelW(5u, L"Remove readonly attribute from [%s] for writing", a2);
      FileAttributesW &= ~1u;
      if ( SetFileAttributesW(a2, FileAttributesW) )
      {
        v7 = 1;
      }
      else
      {
        v10 = GetLastError();
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        LogLevelW(3u, L"Failed to set file attributes for [%s]. Err=0x%08x", a2, (unsigned int)v10);
      }
    }
    v14[0] = 8;
    v14[1] = v5;
    v11 = *(_QWORD *)this;
    v14[2] = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v11 + 528LL))(v11, v14);
    if ( v7 )
    {
      LogLevelW(5u, L"Restore readonly attribute to [%s] afterwriting", a2);
      if ( !SetFileAttributesW(a2, FileAttributesW | 1) )
      {
        v13 = GetLastError();
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        LogLevelW(3u, L"Failed to set file attributes for [%s]. Err=0x%08x", a2, (unsigned int)v13);
      }
    }
    if ( v12 < 0 )
      LogLevelW(2u, L"Failed to save document to %s. Err=0x%08x", a2, (unsigned int)v12);
    SysFreeString(v5);
    return (unsigned int)v12;
  }
  else
  {
    LogLevelW(2u, L"Failed to allocate path");
    SysFreeString(0);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180049758  push    rbx
0x18004975a  push    rbp
0x18004975b  push    rsi
0x18004975c  push    rdi
0x18004975d  push    r14
0x18004975f  push    r15
0x180049761  sub     rsp, 48h
0x180049765  mov     rdi, rdx
0x180049768  mov     r15, rcx
0x18004976b  mov     rcx, rdx; psz
0x18004976e  call    cs:__imp_SysAllocString
0x180049774  xor     ebx, ebx
0x180049776  mov     [rsp+78h+arg_10], rbx
0x18004977e  test    rax, rax
0x180049781  jz      short loc_180049797
0x180049783  mov     rcx, rax; psz
0x180049786  call    cs:__imp_SysAllocString
0x18004978c  mov     rbx, rax
0x18004978f  mov     [rsp+78h+arg_10], rax
0x180049797  test    rbx, rbx
0x18004979a  jnz     short loc_1800497BE
0x18004979c  lea     rdx, aFailedToAlloca_13; "Failed to allocate path"
0x1800497a3  lea     ecx, [rbx+2]; unsigned __int8
0x1800497a6  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800497ab  nop
0x1800497ac  xor     ecx, ecx; bstrString
0x1800497ae  call    cs:__imp_SysFreeString
0x1800497b4  mov     eax, 8007000Eh
0x1800497b9  jmp     loc_180049914
0x1800497be  xor     r14b, r14b
0x1800497c1  mov     rcx, rdi; lpFileName
0x1800497c4  call    cs:__imp_GetFileAttributesW
0x1800497ca  mov     esi, eax
0x1800497cc  cmp     eax, 0FFFFFFFFh
0x1800497cf  jnz     short loc_1800497EC
0x1800497d1  call    cs:__imp_GetLastError
0x1800497d7  test    eax, eax
0x1800497d9  jle     short loc_1800497E3
0x1800497db  movzx   eax, ax
0x1800497de  or      eax, 80070000h
0x1800497e3  lea     rdx, aFailedToGetFil; "Failed to get file attributes for [%s]."...
0x1800497ea  jmp     short loc_180049845
0x1800497ec  test    sil, 1
0x1800497f0  jbe     short loc_18004985A
0x1800497f2  mov     r8, rdi
0x1800497f5  lea     rdx, aXmlFileSIsRead; "Xml file [%s] is readonly"
0x1800497fc  mov     ecx, 4; unsigned __int8
0x180049801  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180049806  mov     r8, rdi
0x180049809  lea     rdx, aRemoveReadonly; "Remove readonly attribute from [%s] for"...
0x180049810  mov     ecx, 5; unsigned __int8
0x180049815  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004981a  and     esi, 0FFFFFFFEh
0x18004981d  mov     edx, esi; dwFileAttributes
0x18004981f  mov     rcx, rdi; lpFileName
0x180049822  call    cs:__imp_SetFileAttributesW
0x180049828  test    eax, eax
0x18004982a  jnz     short loc_180049857
0x18004982c  call    cs:__imp_GetLastError
0x180049832  test    eax, eax
0x180049834  jle     short loc_18004983E
0x180049836  movzx   eax, ax
0x180049839  or      eax, 80070000h
0x18004983e  lea     rdx, aFailedToSetFil; "Failed to set file attributes for [%s]."...
0x180049845  mov     r8, rdi
0x180049848  mov     r9d, eax
0x18004984b  mov     ecx, 3; unsigned __int8
0x180049850  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180049855  jmp     short loc_18004985A
0x180049857  mov     r14b, 1
0x18004985a  xorps   xmm0, xmm0
0x18004985d  xor     edx, edx
0x18004985f  movups  [rsp+78h+var_58], xmm0
0x180049864  lea     eax, [rdx+8]
0x180049867  mov     word ptr [rsp+78h+var_58], ax
0x18004986c  mov     qword ptr [rsp+78h+var_58+8], rbx
0x180049871  mov     rcx, [r15]
0x180049874  movups  xmm0, [rsp+78h+var_58]
0x180049879  movaps  [rsp+78h+var_58], xmm0
0x18004987e  mov     [rsp+78h+var_48], rdx
0x180049883  mov     rax, [rcx]
0x180049886  lea     rdx, [rsp+78h+var_58]
0x18004988b  mov     rax, [rax+210h]
0x180049892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049897  mov     ebp, eax
0x180049899  test    r14b, r14b
0x18004989c  jz      short loc_1800498ED
0x18004989e  mov     r8, rdi
0x1800498a1  lea     rdx, aRestoreReadonl; "Restore readonly attribute to [%s] afte"...
0x1800498a8  mov     ecx, 5; unsigned __int8
0x1800498ad  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800498b2  or      esi, 1
0x1800498b5  mov     edx, esi; dwFileAttributes
0x1800498b7  mov     rcx, rdi; lpFileName
0x1800498ba  call    cs:__imp_SetFileAttributesW
0x1800498c0  test    eax, eax
0x1800498c2  jnz     short loc_1800498ED
0x1800498c4  call    cs:__imp_GetLastError
0x1800498ca  test    eax, eax
0x1800498cc  jle     short loc_1800498D6
0x1800498ce  movzx   eax, ax
0x1800498d1  or      eax, 80070000h
0x1800498d6  mov     r9d, eax
0x1800498d9  mov     r8, rdi
0x1800498dc  lea     rdx, aFailedToSetFil; "Failed to set file attributes for [%s]."...
0x1800498e3  mov     ecx, 3; unsigned __int8
0x1800498e8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800498ed  test    ebp, ebp
0x1800498ef  jns     short loc_180049909
0x1800498f1  mov     r9d, ebp
0x1800498f4  mov     r8, rdi
0x1800498f7  lea     rdx, aFailedToSaveDo; "Failed to save document to %s. Err=0x%0"...
0x1800498fe  mov     ecx, 2; unsigned __int8
0x180049903  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180049908  nop
0x180049909  mov     rcx, rbx; bstrString
0x18004990c  call    cs:__imp_SysFreeString
0x180049912  mov     eax, ebp
0x180049914  add     rsp, 48h
0x180049918  pop     r15
0x18004991a  pop     r14
0x18004991c  pop     rdi
0x18004991d  pop     rsi
0x18004991e  pop     rbp
0x18004991f  pop     rbx
0x180049920  retn
```
