# CWinSATTaskMangerTask::SQMLogWinSATRun(ulong,unsigned __int64)

- ea: `0x180021f00`
- end: `0x180022080`
- name: `?SQMLogWinSATRun@CWinSATTaskMangerTask@@AEAAXK_K@Z`
- size: `384`
- prototype: `void __fastcall(CWinSATTaskMangerTask *__hidden this, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800209a8`

## callees

- `0x18000f0e8`
- `0x18001b5d8`
- `0x18001b790`
- `0x180021afc`
- `0x180021f00`
- `0x18002d650`
- `0x18002d76c`
- `0x180033010`

## string_xrefs

- `0x180021f50`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021f41`: `cannot read the task error count from the registry`
- `0x180022012`: `Cannot write %s to the registry`
- `0x180021f7d`: `base\winsat\api-dll\winsattaskmangertasksqm.cpp`
- `0x180022021`: `base\winsat\api-dll\winsattaskmangertasksqm.cpp`

## pseudocode

```c
void __fastcall CWinSATTaskMangerTask::SQMLogWinSATRun(CWinSATTaskMangerTask *this, int a2, unsigned __int64 a3)
{
  unsigned int v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rdi
  void (__fastcall *v10)(void *, __int64, _QWORD); // rax
  unsigned int v11; // eax
  void (__fastcall *v12)(void *, __int64, __int64); // rax
  char v13; // [rsp+20h] [rbp-28h]
  bool v14; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int64 v15; // [rsp+68h] [rbp+20h] BYREF

  if ( a2 == 1 )
  {
    v15 = 0;
    v14 = 0;
    v5 = RegHelper::ReadQWORDValue(0, L"WindeployTimeDate", &v15);
    if ( v5 )
    {
      Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", 0xC4u, v5, v13);
      v7 = 65532;
    }
    else
    {
      v8 = v15;
      if ( v14 )
        v8 = 0;
      if ( v8 )
      {
        if ( v8 < a3 )
        {
          v9 = a3 - v8;
          if ( v9 < 0xFFFF )
          {
            v7 = v9;
            Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertasksqm.cpp", 86, "Seconds Since WinDeploy = %u", v9);
          }
          else
          {
            v7 = 65534;
            Record_InternalError_w(
              "base\\winsat\\api-dll\\winsattaskmangertasksqm.cpp",
              0x4Eu,
              (wchar_t *)L"Windeploy time difference is greater than 32 bits can hold");
          }
        }
        else
        {
          Record_InternalError_w(
            "base\\winsat\\api-dll\\winsattaskmangertasksqm.cpp",
            0x40u,
            (wchar_t *)L"Windeploy time is greater than the time now");
          v7 = 0xFFFF;
        }
      }
      else
      {
        v7 = 65533;
      }
    }
    v10 = (void (__fastcall *)(void *, __int64, _QWORD))*((_QWORD *)this + 17);
    if ( v10 )
      v10(&unk_18004A8B0, 6435, v7);
    v11 = RegHelper::WriteDWORDValue(v6, L"WinDeployToFirstRunDuration", v7);
    if ( v11 )
      Record_Win32Error_w(
        "base\\winsat\\api-dll\\winsattaskmangertasksqm.cpp",
        0x66u,
        v11,
        (char)L"WinDeployToFirstRunDuration");
  }
  v14 = 0;
  if ( CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(this, &v14) && !v14 )
  {
    v12 = (void (__fastcall *)(void *, __int64, __int64))*((_QWORD *)this + 20);
    if ( v12 )
      v12(&unk_18004A8B0, 6437, 1);
  }
}

```

## disassembly

```asm
0x180021f00  mov     rax, rsp
0x180021f03  mov     [rax+8], rbx
0x180021f07  push    rbp
0x180021f08  push    rsi
0x180021f09  push    rdi
0x180021f0a  sub     rsp, 30h
0x180021f0e  xor     ebp, ebp
0x180021f10  mov     rdi, r8
0x180021f13  mov     rsi, rcx
0x180021f16  cmp     edx, 1
0x180021f19  jnz     loc_180022032
0x180021f1f  lea     r9, [rax+10h]
0x180021f23  mov     [rax+20h], rbp
0x180021f27  lea     r8, [rax+20h]
0x180021f2b  mov     [rax+10h], bpl
0x180021f2f  lea     rdx, aWindeploytimed; "WindeployTimeDate"
0x180021f36  xor     ecx, ecx
0x180021f38  call    ?ReadQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEA_KPEA_N@Z; RegHelper::ReadQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64 &,bool *)
0x180021f3d  test    eax, eax
0x180021f3f  jz      short loc_180021F63
0x180021f41  lea     r9, aCannotReadTheT; "cannot read the task error count from t"...
0x180021f48  mov     r8d, eax; unsigned int
0x180021f4b  mov     edx, 0C4h; unsigned int
0x180021f50  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021f57  call    Record_Win32Error_w
0x180021f5c  mov     ebx, 0FFFCh
0x180021f61  jmp     short loc_180021FDC
0x180021f63  cmp     [rsp+48h+arg_8], bpl
0x180021f68  mov     rax, [rsp+48h+arg_18]
0x180021f6d  cmovnz  rax, rbp
0x180021f71  test    rax, rax
0x180021f74  jnz     short loc_180021F7D
0x180021f76  mov     ebx, 0FFFDh
0x180021f7b  jmp     short loc_180021FDC
0x180021f7d  lea     rcx, aBaseWinsatApiD_2; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021f84  cmp     rax, rdi
0x180021f87  jb      short loc_180021FA1
0x180021f89  lea     r8, aWindeployTimeI; "Windeploy time is greater than the time"...
0x180021f90  mov     edx, 40h ; '@'; unsigned int
0x180021f95  call    Record_InternalError_w
0x180021f9a  mov     ebx, 0FFFFh
0x180021f9f  jmp     short loc_180021FDC
0x180021fa1  sub     rdi, rax
0x180021fa4  mov     ebx, 0FFFFh
0x180021fa9  cmp     rdi, rbx
0x180021fac  jb      short loc_180021FC6
0x180021fae  lea     r8, aWindeployTimeD; "Windeploy time difference is greater th"...
0x180021fb5  mov     edx, 4Eh ; 'N'; unsigned int
0x180021fba  mov     ebx, 0FFFEh
0x180021fbf  call    Record_InternalError_w
0x180021fc4  jmp     short loc_180021FDC
0x180021fc6  mov     r9d, edi
0x180021fc9  lea     r8, aSecondsSinceWi; "Seconds Since WinDeploy = %u"
0x180021fd0  mov     edx, 56h ; 'V'
0x180021fd5  mov     ebx, edi
0x180021fd7  call    Log_Text_F
0x180021fdc  mov     rax, [rsi+88h]
0x180021fe3  test    rax, rax
0x180021fe6  jz      short loc_180021FFC
0x180021fe8  mov     r8d, ebx
0x180021feb  lea     rcx, unk_18004A8B0
0x180021ff2  mov     edx, 1923h
0x180021ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ffc  mov     r8d, ebx
0x180021fff  lea     rbx, aWindeploytofir; "WinDeployToFirstRunDuration"
0x180022006  mov     rdx, rbx
0x180022009  call    ?WriteDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGK@Z; RegHelper::WriteDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong)
0x18002200e  test    eax, eax
0x180022010  jz      short loc_180022032
0x180022012  lea     r9, aCannotWriteSTo; "Cannot write %s to the registry"
0x180022019  mov     qword ptr [rsp+48h+var_28], rbx; char
0x18002201e  mov     r8d, eax; unsigned int
0x180022021  lea     rcx, aBaseWinsatApiD_2; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180022028  mov     edx, 66h ; 'f'; unsigned int
0x18002202d  call    Record_Win32Error_w
0x180022032  lea     rdx, [rsp+48h+arg_8]; bool *
0x180022037  mov     [rsp+48h+arg_8], bpl
0x18002203c  mov     rcx, rsi; this
0x18002203f  call    ?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z; CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)
0x180022044  test    al, al
0x180022046  jz      short loc_180022072
0x180022048  cmp     [rsp+48h+arg_8], bpl
0x18002204d  jnz     short loc_180022072
0x18002204f  mov     rax, [rsi+0A0h]
0x180022056  test    rax, rax
0x180022059  jz      short loc_180022072
0x18002205b  mov     edx, 1925h
0x180022060  lea     rcx, unk_18004A8B0
0x180022067  mov     r8d, 1
0x18002206d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022072  mov     rbx, [rsp+48h+arg_0]
0x180022077  add     rsp, 30h
0x18002207b  pop     rdi
0x18002207c  pop     rsi
0x18002207d  pop     rbp
0x18002207e  retn
```
