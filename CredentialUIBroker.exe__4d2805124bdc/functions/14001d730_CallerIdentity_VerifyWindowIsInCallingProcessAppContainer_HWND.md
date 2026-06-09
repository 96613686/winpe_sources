# CallerIdentity::VerifyWindowIsInCallingProcessAppContainer(HWND__ *)

- ea: `0x14001d730`
- end: `0x14001d8d6`
- name: `?VerifyWindowIsInCallingProcessAppContainer@CallerIdentity@@YAJPEAUHWND__@@@Z`
- size: `422`
- prototype: `__int64 __fastcall(CallerIdentity *this, HWND, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140018cf8`

## callees

- `0x14000e920`
- `0x14001d1ec`
- `0x14001d320`
- `0x14001d4b0`
- `0x14001d730`
- `0x14001d8dc`
- `0x14001d968`
- `0x14001f010`

## import_xrefs

- `KERNEL32!GetProcessId` at `0x14001d80d`
- `KERNEL32!GetProcessId` at `0x14001d80d`
- `KERNEL32!CloseHandle` at `0x14001d8c3`
- `KERNEL32!CloseHandle` at `0x14001d8c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d7b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d824`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d8a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d7b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d824`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d8a7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001d7fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001d7fd`

## pseudocode

```c
__int64 __fastcall CallerIdentity::VerifyWindowIsInCallingProcessAppContainer(CallerIdentity *this, HWND a2, void **a3)
{
  HRESULT CallingProcessHandle; // ebx
  bool *v5; // r8
  void *v6; // r8
  unsigned __int16 **v7; // r8
  struct IUnknown *v8; // r9
  DWORD ProcessId; // eax
  LPVOID v10; // rsi
  DWORD v11; // edi
  __int64 (__fastcall *v12)(LPVOID, _QWORD, LPVOID *, _QWORD, _QWORD, _QWORD); // rbx
  char *v13; // rcx
  unsigned __int16 *v15[2]; // [rsp+40h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+38h] BYREF
  HANDLE Process; // [rsp+90h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+48h] BYREF

  Process = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle((CallerIdentity *)0x1000, (unsigned int)&Process, a3);
  if ( CallingProcessHandle >= 0 )
  {
    LOBYTE(ppv) = 0;
    CallingProcessHandle = CallerIdentity::IsProcessAppContainer((CallerIdentity *)Process, &ppv, v5);
    if ( CallingProcessHandle >= 0 )
    {
      if ( (_BYTE)ppv )
      {
        CallingProcessHandle = CallerIdentity::VerifyWindowIsInProcessByAppContainerSid(this, (HWND)Process, v6);
        if ( CallingProcessHandle < 0 )
        {
          pv = 0;
          v15[0] = 0;
          CoTaskMemFree(0);
          if ( (int)CallerIdentity::GetProcessAppId(Process, &pv, v7) >= 0 )
            goto LABEL_11;
          ppv = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
          CallingProcessHandle = CoCreateInstance(
                                   &GUID_660b90c8_73a9_4b58_8cae_355b7f55341b,
                                   0,
                                   3u,
                                   &GUID_de25675a_72de_44b4_9373_05170450c140,
                                   &ppv);
          if ( CallingProcessHandle >= 0 )
          {
            ProcessId = GetProcessId(Process);
            v10 = ppv;
            v11 = ProcessId;
            v12 = *(__int64 (__fastcall **)(LPVOID, _QWORD, LPVOID *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppv + 48LL);
            CoTaskMemFree(pv);
            CallingProcessHandle = v12(v10, v11, &pv, 0, 0, 0);
            if ( CallingProcessHandle >= 0 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v15);
              CallingProcessHandle = (**(__int64 (__fastcall ***)(LPVOID, GUID *, unsigned __int16 **))ppv)(
                                       ppv,
                                       &GUID_00000000_0000_0000_c000_000000000046,
                                       v15);
            }
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
          if ( CallingProcessHandle >= 0 )
LABEL_11:
            CallingProcessHandle = CallerIdentity::VerifyWindowIsInSpecifiedApplication(this, (HWND)pv, v15[0], v8);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v15);
          CoTaskMemFree(pv);
        }
      }
      else
      {
        CallingProcessHandle = 1;
      }
    }
  }
  v13 = (char *)Process;
  Process = 0;
  if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v13);
  return (unsigned int)CallingProcessHandle;
}

```

## disassembly

```asm
0x14001d730  push    rbp
0x14001d732  push    rbx
0x14001d733  push    rsi
0x14001d734  push    rdi
0x14001d735  push    r14
0x14001d737  mov     rbp, rsp
0x14001d73a  sub     rsp, 50h
0x14001d73e  mov     r14, rcx
0x14001d741  mov     [rbp+Process], 0
0x14001d749  mov     ecx, 1000h; this
0x14001d74e  lea     rdx, [rbp+Process]; unsigned int
0x14001d752  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x14001d757  mov     ebx, eax
0x14001d759  test    eax, eax
0x14001d75b  js      loc_14001D8AD
0x14001d761  mov     rcx, [rbp+Process]; this
0x14001d765  lea     rdx, [rbp+arg_8]; void *
0x14001d769  mov     byte ptr [rbp+arg_8], 0
0x14001d76d  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x14001d772  mov     ebx, eax
0x14001d774  test    eax, eax
0x14001d776  js      loc_14001D8AD
0x14001d77c  cmp     byte ptr [rbp+arg_8], 0
0x14001d780  jnz     short loc_14001D78C
0x14001d782  mov     ebx, 1
0x14001d787  jmp     loc_14001D8AD
0x14001d78c  mov     rdx, [rbp+Process]; HWND
0x14001d790  mov     rcx, r14; this
0x14001d793  call    ?VerifyWindowIsInProcessByAppContainerSid@CallerIdentity@@YAJPEAUHWND__@@PEAX@Z; CallerIdentity::VerifyWindowIsInProcessByAppContainerSid(HWND__ *,void *)
0x14001d798  mov     ebx, eax
0x14001d79a  test    eax, eax
0x14001d79c  jns     loc_14001D8AD
0x14001d7a2  xor     ecx, ecx; pv
0x14001d7a4  mov     [rbp+pv], 0
0x14001d7ac  mov     [rbp+var_10], 0
0x14001d7b4  call    cs:__imp_CoTaskMemFree
0x14001d7ba  mov     rcx, [rbp+Process]; ProcessHandle
0x14001d7be  lea     rdx, [rbp+pv]; void *
0x14001d7c2  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x14001d7c7  test    eax, eax
0x14001d7c9  jns     loc_14001D888
0x14001d7cf  lea     rcx, [rbp+arg_8]
0x14001d7d3  mov     [rbp+arg_8], 0
0x14001d7db  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001d7e0  xor     edx, edx; pUnkOuter
0x14001d7e2  lea     rax, [rbp+arg_8]
0x14001d7e6  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x14001d7ed  mov     [rsp+50h+ppv], rax; ppv
0x14001d7f2  lea     rcx, _GUID_660b90c8_73a9_4b58_8cae_355b7f55341b; rclsid
0x14001d7f9  lea     r8d, [rdx+3]; dwClsContext
0x14001d7fd  call    cs:__imp_CoCreateInstance
0x14001d803  mov     ebx, eax
0x14001d805  test    eax, eax
0x14001d807  js      short loc_14001D87B
0x14001d809  mov     rcx, [rbp+Process]; Process
0x14001d80d  call    cs:__imp_GetProcessId
0x14001d813  mov     rsi, [rbp+arg_8]
0x14001d817  mov     edi, eax
0x14001d819  mov     rcx, [rbp+pv]; pv
0x14001d81d  mov     rdx, [rsi]
0x14001d820  mov     rbx, [rdx+30h]
0x14001d824  call    cs:__imp_CoTaskMemFree
0x14001d82a  xor     r9d, r9d
0x14001d82d  mov     [rsp+50h+var_28], 0
0x14001d836  lea     r8, [rbp+pv]
0x14001d83a  mov     [rsp+50h+ppv], 0
0x14001d843  mov     edx, edi
0x14001d845  mov     rcx, rsi
0x14001d848  mov     rax, rbx
0x14001d84b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d850  mov     ebx, eax
0x14001d852  test    eax, eax
0x14001d854  js      short loc_14001D87B
0x14001d856  lea     rcx, [rbp+var_10]
0x14001d85a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001d85f  mov     rcx, [rbp+arg_8]
0x14001d863  lea     r8, [rbp+var_10]
0x14001d867  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14001d86e  mov     rax, [rcx]
0x14001d871  mov     rax, [rax]
0x14001d874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d879  mov     ebx, eax
0x14001d87b  lea     rcx, [rbp+arg_8]
0x14001d87f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001d884  test    ebx, ebx
0x14001d886  js      short loc_14001D89A
0x14001d888  mov     r8, [rbp+var_10]; unsigned __int16 *
0x14001d88c  mov     rcx, r14; this
0x14001d88f  mov     rdx, [rbp+pv]; HWND
0x14001d893  call    ?VerifyWindowIsInSpecifiedApplication@CallerIdentity@@YAJPEAUHWND__@@PEBGPEAUIUnknown@@@Z; CallerIdentity::VerifyWindowIsInSpecifiedApplication(HWND__ *,ushort const *,IUnknown *)
0x14001d898  mov     ebx, eax
0x14001d89a  lea     rcx, [rbp+var_10]
0x14001d89e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001d8a3  mov     rcx, [rbp+pv]; pv
0x14001d8a7  call    cs:__imp_CoTaskMemFree
0x14001d8ad  mov     rcx, [rbp+Process]; hObject
0x14001d8b1  mov     [rbp+Process], 0
0x14001d8b9  lea     rax, [rcx-1]
0x14001d8bd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001d8c1  ja      short loc_14001D8C9
0x14001d8c3  call    cs:__imp_CloseHandle
0x14001d8c9  mov     eax, ebx
0x14001d8cb  add     rsp, 50h
0x14001d8cf  pop     r14
0x14001d8d1  pop     rdi
0x14001d8d2  pop     rsi
0x14001d8d3  pop     rbx
0x14001d8d4  pop     rbp
0x14001d8d5  retn
```
