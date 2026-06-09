# _AppxUriToResourceUri(IUri *,ushort const *,ushort * *)

- ea: `0x180054678`
- end: `0x180054850`
- name: `?_AppxUriToResourceUri@@YAJPEAUIUri@@PEBGPEAPEAG@Z`
- size: `472`
- prototype: `__int64 __fastcall(struct IUri *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180054b38`

## callees

- `0x18000a8fc`
- `0x180033c88`
- `0x180054678`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005481b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005481b`

## pseudocode

```c
__int64 __fastcall _AppxUriToResourceUri(struct IUri *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  struct IUriVtbl *lpVtbl; // rax
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdi
  unsigned __int64 v9; // rdx
  void *v10; // rdi
  __int64 v12; // [rsp+30h] [rbp-10h] BYREF
  __int64 v13; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v14; // [rsp+60h] [rbp+20h] BYREF
  __int64 v15; // [rsp+70h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF

  *a3 = 0;
  lpVtbl = a1->lpVtbl;
  v12 = 0;
  v6 = ((__int64 (__fastcall *)(struct IUri *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a1,
         &GUID_e982ce48_0b96_440c_bc37_0c869b27a29e,
         &v12);
  if ( v6 >= 0 )
  {
    v15 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v12 + 32LL))(v12, 0, 0, &v15);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v15 + 176LL))(v15, L"ms-resource");
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v15 + 136LL))(v15, a2);
        if ( v6 >= 0 )
        {
          v13 = 0;
          v14 = 0;
          v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *, __int64 *))(*(_QWORD *)v15 + 88LL))(v15, &v14, &v13);
          if ( v6 >= 0 )
          {
            v8 = v14;
            pv = 0;
            v6 = _AllocArray<unsigned short,CTCoAllocPolicy>(v7, 1, v14 + 6LL, &pv);
            if ( v6 >= 0 )
            {
              v9 = v8 + 6;
              v10 = pv;
              v6 = StringCchPrintfW((unsigned __int16 *)pv, v9, L"%s%s", L"Files", v13);
              if ( v6 >= 0 )
              {
                v6 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v15 + 152LL))(v15, v10);
                if ( v6 >= 0 )
                {
                  pv = 0;
                  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, LPVOID *))(*(_QWORD *)v15 + 24LL))(
                         v15,
                         0,
                         0,
                         &pv);
                  if ( v6 >= 0 )
                  {
                    v6 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 **))(*(_QWORD *)pv + 56LL))(pv, a3);
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
                  }
                }
              }
              CoTaskMemFree(v10);
            }
          }
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180054678  mov     [rsp-18h+arg_8], rbx
0x18005467d  push    rbp
0x18005467e  push    rsi
0x18005467f  push    rdi
0x180054680  mov     rbp, rsp
0x180054683  sub     rsp, 40h
0x180054687  mov     qword ptr [r8], 0
0x18005468e  mov     rsi, r8
0x180054691  mov     rax, [rcx]
0x180054694  lea     r8, [rbp+var_10]
0x180054698  mov     rdi, rdx
0x18005469b  mov     [rbp+var_10], 0
0x1800546a3  lea     rdx, _GUID_e982ce48_0b96_440c_bc37_0c869b27a29e
0x1800546aa  mov     rax, [rax]
0x1800546ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800546b2  mov     ebx, eax
0x1800546b4  test    eax, eax
0x1800546b6  js      loc_180054841
0x1800546bc  mov     rcx, [rbp+var_10]
0x1800546c0  lea     r9, [rbp+arg_10]
0x1800546c4  mov     [rbp+arg_10], 0
0x1800546cc  xor     r8d, r8d
0x1800546cf  xor     edx, edx
0x1800546d1  mov     rax, [rcx]
0x1800546d4  mov     rax, [rax+20h]
0x1800546d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800546dd  mov     ebx, eax
0x1800546df  test    eax, eax
0x1800546e1  js      loc_180054831
0x1800546e7  mov     rcx, [rbp+arg_10]
0x1800546eb  lea     rdx, aMsResource; "ms-resource"
0x1800546f2  mov     rax, [rcx]
0x1800546f5  mov     rax, [rax+0B0h]
0x1800546fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054701  mov     ebx, eax
0x180054703  test    eax, eax
0x180054705  js      loc_180054821
0x18005470b  mov     rcx, [rbp+arg_10]
0x18005470f  mov     rdx, rdi
0x180054712  mov     rax, [rcx]
0x180054715  mov     rax, [rax+88h]
0x18005471c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054721  mov     ebx, eax
0x180054723  test    eax, eax
0x180054725  js      loc_180054821
0x18005472b  mov     rcx, [rbp+arg_10]
0x18005472f  lea     r8, [rbp+var_8]
0x180054733  mov     [rbp+var_8], 0
0x18005473b  lea     rdx, [rbp+arg_0]
0x18005473f  mov     [rbp+arg_0], 0
0x180054746  mov     rax, [rcx]
0x180054749  mov     rax, [rax+58h]
0x18005474d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054752  mov     ebx, eax
0x180054754  test    eax, eax
0x180054756  js      loc_180054821
0x18005475c  mov     edi, [rbp+arg_0]
0x18005475f  lea     r9, [rbp+pv]
0x180054763  mov     edx, 1
0x180054768  mov     [rbp+pv], 0
0x180054770  lea     r8, [rdi+6]
0x180054774  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x180054779  mov     ebx, eax
0x18005477b  test    eax, eax
0x18005477d  js      loc_180054821
0x180054783  mov     rax, [rbp+var_8]
0x180054787  lea     rdx, [rdi+6]; unsigned __int64
0x18005478b  mov     rdi, [rbp+pv]
0x18005478f  lea     r9, aFiles; "Files"
0x180054796  mov     rcx, rdi; unsigned __int16 *
0x180054799  mov     [rsp+40h+var_20], rax
0x18005479e  lea     r8, aSS; "%s%s"
0x1800547a5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800547aa  mov     ebx, eax
0x1800547ac  test    eax, eax
0x1800547ae  js      short loc_180054818
0x1800547b0  mov     rcx, [rbp+arg_10]
0x1800547b4  mov     rdx, rdi
0x1800547b7  mov     rax, [rcx]
0x1800547ba  mov     rax, [rax+98h]
0x1800547c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800547c6  mov     ebx, eax
0x1800547c8  test    eax, eax
0x1800547ca  js      short loc_180054818
0x1800547cc  mov     rcx, [rbp+arg_10]
0x1800547d0  lea     r9, [rbp+pv]
0x1800547d4  mov     [rbp+pv], 0
0x1800547dc  xor     r8d, r8d
0x1800547df  xor     edx, edx
0x1800547e1  mov     rax, [rcx]
0x1800547e4  mov     rax, [rax+18h]
0x1800547e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800547ed  mov     ebx, eax
0x1800547ef  test    eax, eax
0x1800547f1  js      short loc_180054818
0x1800547f3  mov     rcx, [rbp+pv]
0x1800547f7  mov     rdx, rsi
0x1800547fa  mov     rax, [rcx]
0x1800547fd  mov     rax, [rax+38h]
0x180054801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054806  mov     rcx, [rbp+pv]
0x18005480a  mov     ebx, eax
0x18005480c  mov     rax, [rcx]
0x18005480f  mov     rax, [rax+10h]
0x180054813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054818  mov     rcx, rdi; pv
0x18005481b  call    cs:__imp_CoTaskMemFree
0x180054821  mov     rcx, [rbp+arg_10]
0x180054825  mov     rax, [rcx]
0x180054828  mov     rax, [rax+10h]
0x18005482c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054831  mov     rcx, [rbp+var_10]
0x180054835  mov     rax, [rcx]
0x180054838  mov     rax, [rax+10h]
0x18005483c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054841  mov     eax, ebx
0x180054843  mov     rbx, [rsp+40h+arg_8]
0x180054848  add     rsp, 40h
0x18005484c  pop     rdi
0x18005484d  pop     rsi
0x18005484e  pop     rbp
0x18005484f  retn
```
