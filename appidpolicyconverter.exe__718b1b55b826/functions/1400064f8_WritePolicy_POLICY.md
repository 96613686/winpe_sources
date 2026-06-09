# WritePolicy(_POLICY *)

- ea: `0x1400064f8`
- end: `0x14000684f`
- name: `?WritePolicy@@YAKPEAU_POLICY@@@Z`
- size: `855`
- prototype: `__int64 __fastcall(const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000458c`

## callees

- `0x140005194`
- `0x140005634`
- `0x140005790`
- `0x140006000`
- `0x1400064f8`
- `0x140006858`
- `0x140006fd8`
- `0x140007010`
- `0x140008d30`
- `0x140008ef4`
- `0x1400090d0`
- `0x140013ab7`
- `0x140013b10`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140006693`
- `msvcrt!_wcsicmp` at `0x140006693`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400065db`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000662b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000681b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400065db`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000662b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000681b`

## string_xrefs

- `0x140006689`: `MANAGEDINSTALLER`
- `0x140006555`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

## pseudocode

```c
__int64 __fastcall WritePolicy(const unsigned __int16 **a1)
{
  unsigned int FilePathsAndHandle; // ebx
  unsigned int v4; // r13d
  _DWORD *v5; // rax
  _DWORD *v6; // rbx
  int v7; // eax
  int v8; // ecx
  unsigned int v9; // esi
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned int PolicySecurityDescriptor; // esi
  char *v13; // rsi
  unsigned int v14; // r14d
  unsigned int v15; // r13d
  __int64 v16; // r15
  __int64 v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // r14d
  __int64 v20; // rax
  unsigned int v21; // eax
  unsigned int v22; // r14d
  __int64 v23; // rax
  unsigned int v24; // eax
  unsigned int v25; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v26; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  void *v29; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v32[2]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v33; // [rsp+80h] [rbp-80h]
  unsigned __int16 v34[261]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v35[261]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v29 = (void *)-1LL;
  v26 = 0;
  v25 = 0;
  v33 = 0;
  lpFileName = 0;
  v27 = 0;
  v30[0] = 10879140;
  v30[1] = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\SMARTLOCKER";
  v31[0] = 2621478;
  v31[1] = L"CurrentOriginDataId";
  v32[0] = 2621478;
  v32[1] = L"TrustedOriginDataId";
  FilePathsAndHandle = GetFilePathsAndHandle((unsigned __int16 (*)[261])v35, (unsigned __int16 (*)[261])v34, *a1, &v29);
  std::unique_ptr<void *,release::Deleter<release::handle_tag>>::reset(&v27, &v29);
  std::unique_ptr<unsigned short,release::Deleter<release::delete_file_tag>>::reset(&lpFileName, v34);
  if ( FilePathsAndHandle || (FilePathsAndHandle = GetPolicyFileSize((struct _POLICY *)a1, &v26, &v25)) != 0 )
  {
    std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(&v27);
    if ( lpFileName )
      DeleteFileW(lpFileName);
    return FilePathsAndHandle;
  }
  v4 = v26;
  v5 = (_DWORD *)AiAlloc(v26);
  v6 = v5;
  if ( !v5 )
  {
    std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(&v27);
    if ( lpFileName )
      DeleteFileW(lpFileName);
    return 14;
  }
  v33 = v5;
  *v5 = 1179676737;
  v5[1] = 1;
  v5[7] = *((_DWORD *)a1 + 8);
  v7 = *((_DWORD *)a1 + 2);
  v6[6] = v7;
  v8 = v7 | (4 * *((_DWORD *)a1 + 3));
  v6[6] = v8;
  v6[6] = v8 | (32 * *((_DWORD *)a1 + 4));
  v6[3] = *((_DWORD *)a1 + 9);
  v6[2] = 32;
  v9 = v25;
  v6[5] = v25;
  v6[4] = 28 * *((_DWORD *)a1 + 9) + 32;
  if ( !_wcsicmp(*a1, L"MANAGEDINSTALLER") )
  {
    AiRegWriteDwordValue(v10, v30, v31, *((unsigned int *)a1 + 5));
    AiRegWriteDwordValue(v11, v30, v32, *((unsigned int *)a1 + 6));
  }
  PolicySecurityDescriptor = CreatePolicySecurityDescriptor(
                               (struct _POLICY *)a1,
                               (struct _SECURITY_DESCRIPTOR_RELATIVE *)((char *)v6 + (unsigned int)v6[4]),
                               v9);
  if ( !PolicySecurityDescriptor )
  {
    v13 = (char *)v6 + (unsigned int)v6[2];
    v14 = v6[4] + v6[5];
    v25 = 0;
    if ( *((_DWORD *)a1 + 9) )
    {
      v15 = 0;
      do
      {
        v16 = 28LL * v15;
        *(_DWORD *)&v13[v16 + 24] = *(_DWORD *)&a1[5][20 * v15 + 16];
        *(_DWORD *)&v13[v16] = v14;
        v17 = -1;
        do
          ++v17;
        while ( *(_WORD *)(*(_QWORD *)&a1[5][20 * v15] + 2 * v17) );
        v18 = 2 * v17;
        *(_DWORD *)&v13[v16 + 4] = v18;
        memcpy_0((char *)v6 + v14, *(const void **)&a1[5][20 * v15], v18);
        v19 = *(_DWORD *)&v13[v16 + 4] + v14;
        *(_DWORD *)&v13[v16 + 16] = v19;
        v20 = -1;
        do
          ++v20;
        while ( *(_WORD *)(*(_QWORD *)&a1[5][20 * v15 + 8] + 2 * v20) );
        v21 = 2 * v20;
        *(_DWORD *)&v13[v16 + 20] = v21;
        memcpy_0((char *)v6 + v19, *(const void **)&a1[5][20 * v15 + 8], v21);
        v22 = *(_DWORD *)&v13[v16 + 20] + v19;
        *(_DWORD *)&v13[v16 + 8] = v22;
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)(*(_QWORD *)&a1[5][20 * v15 + 4] + 2 * v23) );
        v24 = 2 * v23;
        *(_DWORD *)&v13[v16 + 12] = v24;
        memcpy_0((char *)v6 + v22, *(const void **)&a1[5][20 * v15 + 4], v24);
        v14 = *(_DWORD *)&v13[v16 + 12] + v22;
        ++v15;
      }
      while ( v15 < *((_DWORD *)a1 + 9) );
      v4 = v26;
    }
    PolicySecurityDescriptor = WriteAndReplaceFile(&v27, &lpFileName, v35, v6, v4);
  }
  std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(&v27);
  if ( lpFileName )
    DeleteFileW(lpFileName);
  AiFree(v6);
  return PolicySecurityDescriptor;
}

```

## disassembly

```asm
0x1400064f8  push    rbp
0x1400064fa  push    rbx
0x1400064fb  push    rsi
0x1400064fc  push    rdi
0x1400064fd  push    r12
0x1400064ff  push    r13
0x140006501  push    r14
0x140006503  push    r15
0x140006505  lea     rbp, [rsp-3C8h]
0x14000650d  sub     rsp, 4C8h
0x140006514  mov     rax, cs:__security_cookie
0x14000651b  xor     rax, rsp
0x14000651e  mov     [rbp+400h+var_50], rax
0x140006525  mov     rdi, rcx
0x140006528  mov     [rsp+500h+var_4B8], 0FFFFFFFFFFFFFFFFh
0x140006531  xor     r15d, r15d
0x140006534  mov     [rsp+500h+var_4CC], r15d
0x140006539  mov     [rsp+500h+var_4D0], r15d
0x14000653e  mov     [rbp+400h+var_480], r15
0x140006542  mov     [rsp+500h+lpFileName], r15
0x140006547  mov     [rsp+500h+var_4C8], r15
0x14000654c  mov     [rsp+500h+var_4B0], 0A600A4h
0x140006555  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x14000655c  mov     [rsp+500h+var_4A8], rax
0x140006561  mov     [rsp+500h+var_4A0], 280026h
0x14000656a  lea     rax, aCurrentorigind; "CurrentOriginDataId"
0x140006571  mov     [rsp+500h+var_498], rax
0x140006576  mov     [rsp+500h+var_490], 280026h
0x14000657f  lea     rax, aTrustedorigind; "TrustedOriginDataId"
0x140006586  mov     [rsp+500h+var_488], rax
0x14000658b  lea     r9, [rsp+500h+var_4B8]; void **
0x140006590  mov     r8, [rcx]; unsigned __int16 *
0x140006593  lea     rdx, [rbp+400h+var_470]; unsigned __int16 (*)[261]
0x140006597  lea     rcx, [rbp+400h+var_260]; unsigned __int16 (*)[261]
0x14000659e  call    ?GetFilePathsAndHandle@@YAKAEAY0BAF@G0PEBGPEAPEAX@Z; GetFilePathsAndHandle(ushort (&)[261],ushort (&)[261],ushort const *,void * *)
0x1400065a3  mov     ebx, eax
0x1400065a5  lea     rdx, [rsp+500h+var_4B8]
0x1400065aa  lea     rcx, [rsp+500h+var_4C8]
0x1400065af  call    ?reset@?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@QEAAXPEAPEAX@Z; std::unique_ptr<void *,release::Deleter<release::handle_tag>>::reset(void * *)
0x1400065b4  lea     rdx, [rbp+400h+var_470]
0x1400065b8  lea     rcx, [rsp+500h+lpFileName]
0x1400065bd  call    ?reset@?$unique_ptr@GU?$Deleter@Udelete_file_tag@release@@@release@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort,release::Deleter<release::delete_file_tag>>::reset(ushort *)
0x1400065c2  test    ebx, ebx
0x1400065c4  jz      short loc_1400065E9
0x1400065c6  lea     rcx, [rsp+500h+var_4C8]
0x1400065cb  call    ?_Delete@?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@AEAAXXZ; std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(void)
0x1400065d0  nop
0x1400065d1  mov     rcx, [rsp+500h+lpFileName]; lpFileName
0x1400065d6  test    rcx, rcx
0x1400065d9  jz      short loc_1400065E2
0x1400065db  call    cs:__imp_DeleteFileW
0x1400065e1  nop
0x1400065e2  mov     eax, ebx
0x1400065e4  jmp     loc_14000682C
0x1400065e9  lea     r8, [rsp+500h+var_4D0]; unsigned int *
0x1400065ee  lea     rdx, [rsp+500h+var_4CC]; unsigned int *
0x1400065f3  mov     rcx, rdi; struct _POLICY *
0x1400065f6  call    ?GetPolicyFileSize@@YAKPEAU_POLICY@@PEAK1@Z; GetPolicyFileSize(_POLICY *,ulong *,ulong *)
0x1400065fb  mov     ebx, eax
0x1400065fd  test    eax, eax
0x1400065ff  jnz     short loc_1400065C6
0x140006601  mov     r13d, [rsp+500h+var_4CC]
0x140006606  mov     ecx, r13d
0x140006609  call    AiAlloc
0x14000660e  mov     rbx, rax
0x140006611  test    rax, rax
0x140006614  jnz     short loc_140006638
0x140006616  lea     rcx, [rsp+500h+var_4C8]
0x14000661b  call    ?_Delete@?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@AEAAXXZ; std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(void)
0x140006620  nop
0x140006621  mov     rcx, [rsp+500h+lpFileName]; lpFileName
0x140006626  test    rcx, rcx
0x140006629  jz      short loc_140006631
0x14000662b  call    cs:__imp_DeleteFileW
0x140006631  mov     ebx, 0Eh
0x140006636  jmp     short loc_1400065E2
0x140006638  mov     [rbp+400h+var_480], rbx
0x14000663c  mov     dword ptr [rax], 46507041h
0x140006642  mov     dword ptr [rax+4], 1
0x140006649  mov     eax, [rdi+20h]
0x14000664c  mov     [rbx+1Ch], eax
0x14000664f  mov     eax, [rdi+8]
0x140006652  mov     [rbx+18h], eax
0x140006655  mov     ecx, [rdi+0Ch]
0x140006658  shl     ecx, 2
0x14000665b  or      ecx, eax
0x14000665d  mov     [rbx+18h], ecx
0x140006660  mov     eax, [rdi+10h]
0x140006663  shl     eax, 5
0x140006666  or      eax, ecx
0x140006668  mov     [rbx+18h], eax
0x14000666b  mov     eax, [rdi+24h]
0x14000666e  mov     [rbx+0Ch], eax
0x140006671  mov     dword ptr [rbx+8], 20h ; ' '
0x140006678  mov     esi, [rsp+500h+var_4D0]
0x14000667c  mov     [rbx+14h], esi
0x14000667f  imul    eax, [rdi+24h], 1Ch
0x140006683  add     eax, 20h ; ' '
0x140006686  mov     [rbx+10h], eax
0x140006689  lea     rdx, aManagedinstall; "MANAGEDINSTALLER"
0x140006690  mov     rcx, [rdi]; String1
0x140006693  call    cs:__imp__wcsicmp
0x140006699  test    eax, eax
0x14000669b  jnz     short loc_1400066C3
0x14000669d  mov     r9d, [rdi+14h]
0x1400066a1  lea     r8, [rsp+500h+var_4A0]
0x1400066a6  lea     rdx, [rsp+500h+var_4B0]
0x1400066ab  call    AiRegWriteDwordValue
0x1400066b0  mov     r9d, [rdi+18h]
0x1400066b4  lea     r8, [rsp+500h+var_490]
0x1400066b9  lea     rdx, [rsp+500h+var_4B0]
0x1400066be  call    AiRegWriteDwordValue
0x1400066c3  mov     edx, [rbx+10h]
0x1400066c6  add     rdx, rbx; struct _SECURITY_DESCRIPTOR_RELATIVE *
0x1400066c9  mov     r8d, esi; unsigned int
0x1400066cc  mov     rcx, rdi; struct _POLICY *
0x1400066cf  call    ?CreatePolicySecurityDescriptor@@YAKPEAU_POLICY@@PEAU_SECURITY_DESCRIPTOR_RELATIVE@@K@Z; CreatePolicySecurityDescriptor(_POLICY *,_SECURITY_DESCRIPTOR_RELATIVE *,ulong)
0x1400066d4  mov     esi, eax
0x1400066d6  test    eax, eax
0x1400066d8  jnz     loc_140006806
0x1400066de  mov     esi, [rbx+8]
0x1400066e1  add     rsi, rbx
0x1400066e4  mov     r14d, [rbx+14h]
0x1400066e8  add     r14d, [rbx+10h]
0x1400066ec  mov     [rsp+500h+var_4D0], r15d
0x1400066f1  cmp     [rdi+24h], r15d
0x1400066f5  jbe     loc_1400067E6
0x1400066fb  mov     r13d, r15d
0x1400066fe  mov     eax, r13d
0x140006701  lea     r12, [rax+rax*4]
0x140006705  imul    r15, rax, 1Ch
0x140006709  mov     rax, [rdi+28h]
0x14000670d  mov     ecx, [rax+r12*8+20h]
0x140006712  mov     [r15+rsi+18h], ecx
0x140006717  mov     [r15+rsi], r14d
0x14000671b  mov     rax, [rdi+28h]
0x14000671f  mov     rcx, [rax+r12*8]
0x140006723  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006727  xor     edx, edx
0x140006729  inc     rax
0x14000672c  cmp     [rcx+rax*2], dx
0x140006730  jnz     short loc_140006729
0x140006732  add     eax, eax
0x140006734  mov     [r15+rsi+4], eax
0x140006739  mov     r8d, eax; Size
0x14000673c  mov     rdx, [rdi+28h]
0x140006740  mov     ecx, r14d
0x140006743  add     rcx, rbx; void *
0x140006746  mov     rdx, [rdx+r12*8]; Src
0x14000674a  call    memcpy_0
0x14000674f  add     r14d, [r15+rsi+4]
0x140006754  mov     [r15+rsi+10h], r14d
0x140006759  mov     rax, [rdi+28h]
0x14000675d  mov     rcx, [rax+r12*8+10h]
0x140006762  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006766  xor     edx, edx
0x140006768  inc     rax
0x14000676b  cmp     [rcx+rax*2], dx
0x14000676f  jnz     short loc_140006768
0x140006771  add     eax, eax
0x140006773  mov     [r15+rsi+14h], eax
0x140006778  mov     r8d, eax; Size
0x14000677b  mov     rdx, [rdi+28h]
0x14000677f  mov     ecx, r14d
0x140006782  add     rcx, rbx; void *
0x140006785  mov     rdx, [rdx+r12*8+10h]; Src
0x14000678a  call    memcpy_0
0x14000678f  add     r14d, [r15+rsi+14h]
0x140006794  mov     [r15+rsi+8], r14d
0x140006799  mov     rax, [rdi+28h]
0x14000679d  mov     rcx, [rax+r12*8+8]
0x1400067a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400067a6  xor     edx, edx
0x1400067a8  inc     rax
0x1400067ab  cmp     [rcx+rax*2], dx
0x1400067af  jnz     short loc_1400067A8
0x1400067b1  add     eax, eax
0x1400067b3  mov     [r15+rsi+0Ch], eax
0x1400067b8  mov     r8d, eax; Size
0x1400067bb  mov     rdx, [rdi+28h]
0x1400067bf  mov     ecx, r14d
0x1400067c2  add     rcx, rbx; void *
0x1400067c5  mov     rdx, [rdx+r12*8+8]; Src
0x1400067ca  call    memcpy_0
0x1400067cf  add     r14d, [r15+rsi+0Ch]
0x1400067d4  inc     r13d
0x1400067d7  cmp     r13d, [rdi+24h]
0x1400067db  jb      loc_1400066FE
0x1400067e1  mov     r13d, [rsp+500h+var_4CC]
0x1400067e6  mov     [rsp+500h+var_4E0], r13d
0x1400067eb  mov     r9, rbx
0x1400067ee  lea     r8, [rbp+400h+var_260]
0x1400067f5  lea     rdx, [rsp+500h+lpFileName]
0x1400067fa  lea     rcx, [rsp+500h+var_4C8]
0x1400067ff  call    ?WriteAndReplaceFile@@YAKAEAV?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@AEAV?$unique_ptr@GU?$Deleter@Udelete_file_tag@release@@@release@@@2@AEAY0BAF@$$CBGPEBXK@Z; WriteAndReplaceFile(std::unique_ptr<void *,release::Deleter<release::handle_tag>> &,std::unique_ptr<ushort,release::Deleter<release::delete_file_tag>> &,ushort const (&)[261],void const *,ulong)
0x140006804  mov     esi, eax
0x140006806  lea     rcx, [rsp+500h+var_4C8]
0x14000680b  call    ?_Delete@?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@AEAAXXZ; std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(void)
0x140006810  nop
0x140006811  mov     rcx, [rsp+500h+lpFileName]; lpFileName
0x140006816  test    rcx, rcx
0x140006819  jz      short loc_140006822
0x14000681b  call    cs:__imp_DeleteFileW
0x140006821  nop
0x140006822  mov     rcx, rbx
0x140006825  call    AiFree
0x14000682a  mov     eax, esi
0x14000682c  mov     rcx, [rbp+400h+var_50]
0x140006833  xor     rcx, rsp; StackCookie
0x140006836  call    __security_check_cookie
0x14000683b  add     rsp, 4C8h
0x140006842  pop     r15
0x140006844  pop     r14
0x140006846  pop     r13
0x140006848  pop     r12
0x14000684a  pop     rdi
0x14000684b  pop     rsi
0x14000684c  pop     rbx
0x14000684d  pop     rbp
0x14000684e  retn
```
