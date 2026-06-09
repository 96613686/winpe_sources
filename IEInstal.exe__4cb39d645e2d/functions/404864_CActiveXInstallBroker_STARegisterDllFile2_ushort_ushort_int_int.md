# CActiveXInstallBroker::STARegisterDllFile2(ushort *,ushort *,int,int)

- ea: `0x404864`
- end: `0x404948`
- name: `?STARegisterDllFile2@CActiveXInstallBroker@@AAEJPAG0HH@Z`
- size: `228`
- prototype: `DWORD __thiscall(OLECHAR *this, OLECHAR *psz, OLECHAR *, OLECHAR *, OLECHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x404806`

## callees

- `0x4026e7`
- `0x402712`
- `0x404864`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x404907`
- `KERNEL32!CloseHandle` at `0x404907`
- `KERNEL32!CreateThread` at `0x4048c9`
- `KERNEL32!CreateThread` at `0x4048c9`
- `KERNEL32!GetExitCodeThread` at `0x404900`
- `KERNEL32!GetExitCodeThread` at `0x404900`
- `KERNEL32!GetLastError` at `0x4048e2`
- `KERNEL32!GetLastError` at `0x40490f`
- `KERNEL32!GetLastError` at `0x4048e2`
- `KERNEL32!GetLastError` at `0x40490f`
- `KERNEL32!WaitForSingleObject` at `0x4048d8`
- `KERNEL32!WaitForSingleObject` at `0x4048d8`
- `OLEAUT32!__imp__SysAllocString@4` at `0x40488a`
- `OLEAUT32!__imp__SysAllocString@4` at `0x40489e`
- `OLEAUT32!__imp__SysAllocString@4` at `0x40488a`
- `OLEAUT32!__imp__SysAllocString@4` at `0x40489e`
- `OLEAUT32!__imp__SysFreeString@4` at `0x404929`
- `OLEAUT32!__imp__SysFreeString@4` at `0x404932`
- `OLEAUT32!__imp__SysFreeString@4` at `0x404929`
- `OLEAUT32!__imp__SysFreeString@4` at `0x404932`

## pseudocode

```c
DWORD __thiscall CActiveXInstallBroker::STARegisterDllFile2(
        OLECHAR *this,
        OLECHAR *psz,
        OLECHAR *a3,
        OLECHAR *a4,
        OLECHAR *a5)
{
  BSTR *v6; // esi
  BSTR v7; // eax
  BSTR v8; // eax
  HANDLE Thread; // eax
  void *v10; // edi
  signed int LastError; // eax
  DWORD v12; // ecx
  signed int v13; // eax
  DWORD v14; // ecx
  DWORD ExitCode; // [esp+8h] [ebp-4h] BYREF

  ExitCode = -2147024882;
  v6 = (BSTR *)operator new(0x14u);
  if ( v6 )
  {
    v7 = SysAllocString(psz);
    v6[1] = v7;
    if ( v7 )
    {
      v8 = SysAllocString(a3);
      v6[2] = v8;
      if ( v8 )
      {
        v6[3] = a4;
        v6[4] = a5;
        *v6 = this;
        Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CActiveXInstallBroker::RegisterDllFile2ThreadProc, v6, 0, 0);
        v10 = Thread;
        if ( Thread )
        {
          if ( WaitForSingleObject(Thread, 0xFFFFFFFF) )
          {
            LastError = GetLastError();
            v12 = (unsigned __int16)LastError | 0x80070000;
            if ( LastError <= 0 )
              v12 = LastError;
            ExitCode = v12;
          }
          else
          {
            GetExitCodeThread(v10, &ExitCode);
          }
          CloseHandle(v10);
        }
        else
        {
          v13 = GetLastError();
          v14 = (unsigned __int16)v13 | 0x80070000;
          if ( v13 <= 0 )
            v14 = v13;
          ExitCode = v14;
        }
        SysFreeString(v6[2]);
      }
      SysFreeString(v6[1]);
    }
    operator delete(v6);
  }
  return ExitCode;
}

```

## disassembly

```asm
0x404864  mov     edi, edi
0x404866  push    ebp
0x404867  mov     ebp, esp
0x404869  push    ecx
0x40486a  push    esi
0x40486b  push    edi
0x40486c  push    14h; dwBytes
0x40486e  mov     edi, ecx
0x404870  mov     [ebp+ExitCode], 8007000Eh
0x404877  call    ??2@YAPAXI@Z; operator new(uint)
0x40487c  mov     esi, eax
0x40487e  pop     ecx
0x40487f  test    esi, esi
0x404881  jz      loc_40493F
0x404887  push    [ebp+psz]; psz
0x40488a  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x404890  mov     [esi+4], eax
0x404893  test    eax, eax
0x404895  jz      loc_404938
0x40489b  push    [ebp+arg_4]; psz
0x40489e  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x4048a4  mov     [esi+8], eax
0x4048a7  test    eax, eax
0x4048a9  jz      loc_40492F
0x4048af  mov     eax, [ebp+arg_8]
0x4048b2  mov     [esi+0Ch], eax
0x4048b5  mov     eax, [ebp+arg_C]
0x4048b8  mov     [esi+10h], eax
0x4048bb  xor     eax, eax
0x4048bd  push    eax; lpThreadId
0x4048be  push    eax; dwCreationFlags
0x4048bf  push    esi; lpParameter
0x4048c0  push    offset ?RegisterDllFile2ThreadProc@CActiveXInstallBroker@@CGKPAX@Z; lpStartAddress
0x4048c5  push    eax; dwStackSize
0x4048c6  push    eax; lpThreadAttributes
0x4048c7  mov     [esi], edi
0x4048c9  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x4048cf  mov     edi, eax
0x4048d1  test    edi, edi
0x4048d3  jz      short loc_40490F
0x4048d5  push    0FFFFFFFFh; dwMilliseconds
0x4048d7  push    edi; hHandle
0x4048d8  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x4048de  test    eax, eax
0x4048e0  jz      short loc_4048FB
0x4048e2  call    ds:__imp__GetLastError@0; GetLastError()
0x4048e8  movzx   ecx, ax
0x4048eb  or      ecx, 80070000h
0x4048f1  test    eax, eax
0x4048f3  cmovle  ecx, eax
0x4048f6  mov     [ebp+ExitCode], ecx
0x4048f9  jmp     short loc_404906
0x4048fb  lea     eax, [ebp+ExitCode]
0x4048fe  push    eax; lpExitCode
0x4048ff  push    edi; hThread
0x404900  call    ds:__imp__GetExitCodeThread@8; GetExitCodeThread(x,x)
0x404906  push    edi; hObject
0x404907  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x40490d  jmp     short loc_404926
0x40490f  call    ds:__imp__GetLastError@0; GetLastError()
0x404915  movzx   ecx, ax
0x404918  or      ecx, 80070000h
0x40491e  test    eax, eax
0x404920  cmovle  ecx, eax
0x404923  mov     [ebp+ExitCode], ecx
0x404926  push    dword ptr [esi+8]; bstrString
0x404929  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x40492f  push    dword ptr [esi+4]; bstrString
0x404932  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x404938  push    esi; lpMem
0x404939  call    ??3@YAXPAX@Z; operator delete(void *)
0x40493e  pop     ecx
0x40493f  mov     eax, [ebp+ExitCode]
0x404942  pop     edi
0x404943  pop     esi
0x404944  leave
0x404945  retn    10h
```
