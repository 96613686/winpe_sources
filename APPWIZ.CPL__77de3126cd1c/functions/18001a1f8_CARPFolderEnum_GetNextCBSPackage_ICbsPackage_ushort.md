# CARPFolderEnum::_GetNextCBSPackage(ICbsPackage * *,ushort * *)

- ea: `0x18001a1f8`
- end: `0x18001a39c`
- name: `?_GetNextCBSPackage@CARPFolderEnum@@AEAAJPEAPEAUICbsPackage@@PEAPEAG@Z`
- size: `420`
- prototype: `__int64 __fastcall(CARPFolderEnum *__hidden this, struct ICbsPackage **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800153d0`

## callees

- `0x180008cf8`
- `0x180014468`
- `0x18001a1f8`
- `0x18001a778`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a33b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a345`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a33b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a345`

## pseudocode

```c
__int64 __fastcall CARPFolderEnum::_GetNextCBSPackage(CARPFolderEnum *this, struct ICbsPackage **a2, LPVOID *a3)
{
  int v6; // edi
  int v7; // ebx
  __int64 v8; // rcx
  int IsShowableCBSPackage; // eax
  struct ICbsPackage *v10; // rcx
  __int64 v11; // rcx
  PCNZWCH lpString1; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v14[2]; // [rsp+38h] [rbp-10h] BYREF
  int v15; // [rsp+80h] [rbp+38h] BYREF
  struct ICbsPackage *v16; // [rsp+88h] [rbp+40h] BYREF
  __int64 v17; // [rsp+90h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+50h] BYREF

  *a2 = 0;
  *a3 = 0;
  v17 = 0;
  v15 = 0;
  v6 = 0;
  while ( 1 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, int *))(**((_QWORD **)this + 7) + 24LL))(
           *((_QWORD *)this + 7),
           1,
           &v17,
           &v15);
    if ( v7 < 0 || v15 != 1 )
      break;
    v8 = *((_QWORD *)this + 6);
    v14[0] = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _QWORD *))(*(_QWORD *)v8 + 48LL))(v8, 0, v17, 0, v14) >= 0 )
    {
      v16 = 0;
      v7 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct ICbsPackage **))v14[0])(
             v14[0],
             &GUID_75207393_23f2_4396_85f0_8fdb879ed0ed,
             &v16);
      if ( v7 >= 0 )
      {
        lpString1 = 0;
        if ( (*(int (__fastcall **)(struct ICbsPackage *, __int64, PCNZWCH *))(*(_QWORD *)v16 + 32LL))(
               v16,
               8,
               &lpString1) >= 0 )
        {
          if ( GetUpdateReleaseTypeID(lpString1) )
          {
            pv = 0;
            IsShowableCBSPackage = CARPFolderEnum::_IsShowableCBSPackage(this, v16, (unsigned __int16 **)&pv);
            v7 = IsShowableCBSPackage;
            if ( IsShowableCBSPackage )
            {
              if ( IsShowableCBSPackage >= 0 )
                CoTaskMemFree(pv);
            }
            else
            {
              v10 = v16;
              *a2 = v16;
              if ( v10 )
                (*(void (__fastcall **)(struct ICbsPackage *))(*(_QWORD *)v10 + 8LL))(v10);
              v6 = 1;
              *a3 = pv;
            }
          }
          CoTaskMemFree((LPVOID)lpString1);
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    }
    v11 = v17;
    v17 = 0;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v14);
    if ( v7 < 0 || v6 )
      return (unsigned int)v7;
  }
  return 1;
}

```

## disassembly

```asm
0x18001a1f8  push    rbp
0x18001a1fa  push    rbx
0x18001a1fb  push    rsi
0x18001a1fc  push    rdi
0x18001a1fd  push    r14
0x18001a1ff  push    r15
0x18001a201  mov     rbp, rsp
0x18001a204  sub     rsp, 48h
0x18001a208  mov     r14, r8
0x18001a20b  mov     qword ptr [rdx], 0
0x18001a212  mov     rsi, rdx
0x18001a215  mov     qword ptr [r8], 0
0x18001a21c  mov     r15, rcx
0x18001a21f  mov     [rbp+arg_10], 0
0x18001a227  mov     [rbp+arg_0], 0
0x18001a22e  xor     edi, edi
0x18001a230  mov     rcx, [r15+38h]
0x18001a234  lea     r9, [rbp+arg_0]
0x18001a238  lea     r8, [rbp+arg_10]
0x18001a23c  mov     edx, 1
0x18001a241  mov     rax, [rcx]
0x18001a244  mov     rax, [rax+18h]
0x18001a248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a24d  mov     ebx, eax
0x18001a24f  test    eax, eax
0x18001a251  js      loc_18001A388
0x18001a257  cmp     [rbp+arg_0], 1
0x18001a25b  jnz     loc_18001A388
0x18001a261  mov     rcx, [r15+30h]
0x18001a265  xor     r9d, r9d
0x18001a268  mov     r8, [rbp+arg_10]
0x18001a26c  mov     [rbp+var_10], 0
0x18001a274  mov     rdx, [rcx]
0x18001a277  mov     rax, [rdx+30h]
0x18001a27b  lea     rdx, [rbp+var_10]
0x18001a27f  mov     [rsp+48h+var_28], rdx
0x18001a284  xor     edx, edx
0x18001a286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a28b  test    eax, eax
0x18001a28d  js      loc_18001A354
0x18001a293  mov     rcx, [rbp+var_10]
0x18001a297  lea     r8, [rbp+arg_8]
0x18001a29b  mov     [rbp+arg_8], 0
0x18001a2a3  lea     rdx, _GUID_75207393_23f2_4396_85f0_8fdb879ed0ed
0x18001a2aa  mov     rax, [rcx]
0x18001a2ad  mov     rax, [rax]
0x18001a2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2b5  mov     ebx, eax
0x18001a2b7  test    eax, eax
0x18001a2b9  js      loc_18001A34B
0x18001a2bf  mov     rcx, [rbp+arg_8]
0x18001a2c3  lea     r8, [rbp+lpString1]
0x18001a2c7  mov     [rbp+lpString1], 0
0x18001a2cf  mov     edx, 8
0x18001a2d4  mov     rax, [rcx]
0x18001a2d7  mov     rax, [rax+20h]
0x18001a2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2e0  test    eax, eax
0x18001a2e2  js      short loc_18001A34B
0x18001a2e4  mov     rcx, [rbp+lpString1]; lpString1
0x18001a2e8  call    ?GetUpdateReleaseTypeID@@YAKPEBG@Z; GetUpdateReleaseTypeID(ushort const *)
0x18001a2ed  test    eax, eax
0x18001a2ef  jz      short loc_18001A341
0x18001a2f1  mov     rdx, [rbp+arg_8]; struct ICbsPackage *
0x18001a2f5  lea     r8, [rbp+pv]; unsigned __int16 **
0x18001a2f9  mov     rcx, r15; this
0x18001a2fc  mov     [rbp+pv], 0
0x18001a304  call    ?_IsShowableCBSPackage@CARPFolderEnum@@AEAAJPEAUICbsPackage@@PEAPEAG@Z; CARPFolderEnum::_IsShowableCBSPackage(ICbsPackage *,ushort * *)
0x18001a309  mov     ebx, eax
0x18001a30b  test    eax, eax
0x18001a30d  jnz     short loc_18001A335
0x18001a30f  mov     rcx, [rbp+arg_8]
0x18001a313  mov     [rsi], rcx
0x18001a316  test    rcx, rcx
0x18001a319  jz      short loc_18001A327
0x18001a31b  mov     rax, [rcx]
0x18001a31e  mov     rax, [rax+8]
0x18001a322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a327  mov     rax, [rbp+pv]
0x18001a32b  mov     edi, 1
0x18001a330  mov     [r14], rax
0x18001a333  jmp     short loc_18001A341
0x18001a335  js      short loc_18001A341
0x18001a337  mov     rcx, [rbp+pv]; pv
0x18001a33b  call    cs:__imp_CoTaskMemFree
0x18001a341  mov     rcx, [rbp+lpString1]; pv
0x18001a345  call    cs:__imp_CoTaskMemFree
0x18001a34b  lea     rcx, [rbp+arg_8]
0x18001a34f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001a354  mov     rcx, [rbp+arg_10]
0x18001a358  mov     [rbp+arg_10], 0
0x18001a360  test    rcx, rcx
0x18001a363  jz      short loc_18001A371
0x18001a365  mov     rax, [rcx]
0x18001a368  mov     rax, [rax+10h]
0x18001a36c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a371  lea     rcx, [rbp+var_10]
0x18001a375  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001a37a  test    ebx, ebx
0x18001a37c  js      short loc_18001A38D
0x18001a37e  test    edi, edi
0x18001a380  jz      loc_18001A230
0x18001a386  jmp     short loc_18001A38D
0x18001a388  mov     ebx, 1
0x18001a38d  mov     eax, ebx
0x18001a38f  add     rsp, 48h
0x18001a393  pop     r15
0x18001a395  pop     r14
0x18001a397  pop     rdi
0x18001a398  pop     rsi
0x18001a399  pop     rbx
0x18001a39a  pop     rbp
0x18001a39b  retn
```
