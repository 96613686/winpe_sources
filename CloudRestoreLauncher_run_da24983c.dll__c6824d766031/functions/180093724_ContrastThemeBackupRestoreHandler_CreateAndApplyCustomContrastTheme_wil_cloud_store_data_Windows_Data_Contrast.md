# ContrastThemeBackupRestoreHandler::CreateAndApplyCustomContrastTheme(wil::cloud_store_data<Windows::Data::ContrastThemes::SynchedTheme> const &)

- ea: `0x180093724`
- end: `0x1800937c8`
- name: `?CreateAndApplyCustomContrastTheme@ContrastThemeBackupRestoreHandler@@AEAAXAEBV?$cloud_store_data@USynchedTheme@ContrastThemes@Data@Windows@@@wil@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180095170`

## callees

- `0x18001cfa4`
- `0x180061550`
- `0x18008ef40`
- `0x180093724`
- `0x18012d010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x180093782`
- `SHCORE!SHTaskPoolQueueTask` at `0x180093782`

## pseudocode

```c
__int64 __fastcall ContrastThemeBackupRestoreHandler::CreateAndApplyCustomContrastTheme(__int64 a1, __int64 a2)
{
  __int64 *v2; // rax
  __int64 v3; // rbx
  __int64 result; // rax
  int v5; // edi
  _QWORD v6[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  v6[0] = a1;
  v6[1] = a2;
  v2 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_e970e22da30db3f9b003d07b6a073a00_____lambda_e970e22da30db3f9b003d07b6a073a00___(
                    &v8,
                    v6);
  v3 = *v2;
  *v2 = 0;
  if ( v8 )
  {
    v8 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  result = SHTaskPoolQueueTask(1, 32, 0);
  v5 = result;
  if ( v3 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A7,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\contrastthemebackuprestorehandler.cpp",
      (const char *)(unsigned int)v5,
      v3);
  return result;
}

```

## disassembly

```asm
0x180093724  mov     rax, rsp
0x180093727  mov     [rax+10h], rbx
0x18009372b  push    rdi
0x18009372c  sub     rsp, 40h
0x180093730  mov     [rax-18h], rcx
0x180093734  mov     [rax-10h], rdx
0x180093738  lea     rdx, [rax-18h]
0x18009373c  lea     rcx, [rax+8]
0x180093740  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_e970e22da30db3f9b003d07b6a073a00_____lambda_e970e22da30db3f9b003d07b6a073a00___
0x180093745  mov     rbx, [rax]
0x180093748  mov     qword ptr [rax], 0
0x18009374f  mov     rcx, [rsp+48h+arg_0]
0x180093754  test    rcx, rcx
0x180093757  jz      short loc_180093767
0x180093759  mov     [rsp+48h+arg_0], 0
0x180093762  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180093767  mov     [rsp+48h+var_20], 0
0x180093770  mov     qword ptr [rsp+48h+var_28], rbx; int
0x180093775  xor     r9d, r9d
0x180093778  xor     r8d, r8d
0x18009377b  lea     edx, [r9+20h]
0x18009377f  lea     ecx, [rdx-1Fh]
0x180093782  call    cs:__imp_SHTaskPoolQueueTask
0x180093788  mov     edi, eax
0x18009378a  test    rbx, rbx
0x18009378d  jz      short loc_18009379F
0x18009378f  mov     rdx, [rbx]
0x180093792  mov     rcx, rbx
0x180093795  mov     rax, [rdx+10h]
0x180093799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009379e  nop
0x18009379f  test    edi, edi
0x1800937a1  js      short loc_1800937AE
0x1800937a3  mov     rbx, [rsp+48h+arg_8]
0x1800937a8  add     rsp, 40h
0x1800937ac  pop     rdi
0x1800937ad  retn
0x1800937ae  mov     rcx, [rsp+48h]; this
0x1800937b3  mov     r9d, edi; char *
0x1800937b6  lea     r8, aPcshellShellCl_28; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800937bd  mov     edx, 2A7h; void *
0x1800937c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
