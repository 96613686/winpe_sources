# DeleteAllTasks

- ea: `0x18002ae28`
- end: `0x18002b173`
- name: `DeleteAllTasks`
- size: `843`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b9e0`

## callees

- `0x180014e7c`
- `0x18001fb2c`
- `0x18002072c`
- `0x18002ae28`
- `0x18002be88`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18002b04a`
- `OLEAUT32!__imp_VariantClear` at `0x18002b04a`

## string_xrefs

- `0x18002aed7`: `taskService->Connect({}, {}, {}, {})`
- `0x18002af11`: `taskService->GetFolder(L"\\", &folder)`
- `0x18002af75`: `taskService->GetFolder(_bstr_t(NA_TASK_FOLDER), &subFolder)`
- `0x18002afad`: `subFolder->GetTasks(TASK_ENUM_HIDDEN, &tasks)`
- `0x18002afd3`: `tasks->get_Count(&taskCount)`
- `0x18002b0c0`: `tasks->get_Item(_variant_t(taskCount), &task)`
- `0x18002b0b5`: `task->get_Name(&name)`
- `0x18002b0aa`: `subFolder->DeleteTask(name, 0)`
- `0x18002b121`: `folder->DeleteFolder(_bstr_t(NA_TASK_FOLDER), 0)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeleteAllTasks(__int64 *a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // ebx
  const char *v5; // rcx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, const wchar_t *, __int64 *); // rbx
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, _QWORD *, __int64 *); // rdi
  _QWORD *v11; // rdx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64, __int64 **); // rbx
  __int64 *v14; // rdi
  __int64 v15; // rbx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  const char *v19; // rcx
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, _QWORD *, _QWORD); // rdi
  _QWORD *v22; // rdx
  __int64 v24; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+48h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+68h] [rbp-A0h]
  _BYTE v29[16]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v30; // [rsp+88h] [rbp-80h] BYREF
  __int64 v31; // [rsp+98h] [rbp-70h]
  __int128 v32; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v33; // [rsp+B8h] [rbp-50h]
  __int128 v34; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v35; // [rsp+D8h] [rbp-30h]
  int v36; // [rsp+140h] [rbp+38h] BYREF
  __int64 v37; // [rsp+148h] [rbp+40h] BYREF
  __int64 *v38; // [rsp+150h] [rbp+48h] BYREF

  v25 = 0;
  v24 = 0;
  v38 = 0;
  v36 = 0;
  v2 = *a1;
  *(_OWORD *)&pvarg.decVal.Lo32 = 0;
  v28 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v30 = 0;
  v31 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, CY *))(*(_QWORD *)v2 + 80LL))(
         v2,
         &v30,
         &v34,
         &v32,
         &pvarg.cyVal);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = "taskService->Connect({}, {}, {}, {})";
LABEL_5:
    v8 = (unsigned int)v3;
    goto LABEL_6;
  }
  v6 = *a1;
  v7 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)*a1 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  v3 = v7(v6, L"\\", &v25);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = "taskService->GetFolder(L\"\\\\\", &folder)";
    goto LABEL_5;
  }
  v9 = *a1;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)*a1 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  v11 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v37, L"\\Microsoft\\Windows\\NaturalAuthentication");
  if ( v11 )
    v11 = (_QWORD *)*v11;
  v4 = v10(v9, v11, &v24);
  _bstr_t::_Free((_bstr_t *)&v37);
  if ( v4 < 0 )
  {
    v8 = (unsigned int)v4;
    v5 = "taskService->GetFolder(_bstr_t(NA_TASK_FOLDER), &subFolder)";
    goto LABEL_6;
  }
  v12 = v24;
  v13 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)v24 + 112LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  v3 = v13(v12, 1, &v38);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = "subFolder->GetTasks(TASK_ENUM_HIDDEN, &tasks)";
    goto LABEL_5;
  }
  v3 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v38 + 56))(v38, &v36);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = "tasks->get_Count(&taskCount)";
    goto LABEL_5;
  }
  while ( v36 )
  {
    v37 = 0;
    v14 = v38;
    v15 = *v38;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    pvarg.iVal = 3;
    *((_DWORD *)&pvarg.decVal + 4) = v36;
    v30 = *(_OWORD *)&pvarg.decVal.Lo32;
    v31 = v28;
    v4 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64 *))(v15 + 64))(v14, &v30, &v37);
    VariantClear((VARIANTARG *)&pvarg.decVal.8);
    if ( v4 < 0 )
    {
      v18 = (unsigned int)v4;
      v19 = "tasks->get_Item(_variant_t(taskCount), &task)";
      goto LABEL_23;
    }
    v26 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 56LL))(v37, &v26);
    v4 = v16;
    if ( v16 < 0 )
    {
      v18 = (unsigned int)v16;
      v19 = "task->get_Name(&name)";
      goto LABEL_23;
    }
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v24 + 120LL))(v24, v26, 0);
    v4 = v17;
    if ( v17 < 0 )
    {
      v18 = (unsigned int)v17;
      v19 = "subFolder->DeleteTask(name, 0)";
LABEL_23:
      LogOpFailure(v19, v18);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
      goto LABEL_29;
    }
    --v36;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  }
  v20 = v25;
  v21 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v25 + 96LL);
  v22 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v29, L"\\Microsoft\\Windows\\NaturalAuthentication");
  if ( v22 )
    v22 = (_QWORD *)*v22;
  v4 = v21(v20, v22, 0);
  _bstr_t::_Free((_bstr_t *)v29);
  if ( v4 >= 0 )
  {
    v4 = 0;
    goto LABEL_29;
  }
  v8 = (unsigned int)v4;
  v5 = "folder->DeleteFolder(_bstr_t(NA_TASK_FOLDER), 0)";
LABEL_6:
  LogOpFailure(v5, v8);
LABEL_29:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002ae28  mov     rax, rsp
0x18002ae2b  mov     [rax+8], rcx
0x18002ae2f  push    rbp
0x18002ae30  push    rbx
0x18002ae31  push    rsi
0x18002ae32  push    rdi
0x18002ae33  lea     rbp, [rax-28h]
0x18002ae37  sub     rsp, 108h
0x18002ae3e  movaps  xmmword ptr [rax-38h], xmm6
0x18002ae42  movaps  xmmword ptr [rax-48h], xmm7
0x18002ae46  mov     rsi, rcx
0x18002ae49  mov     [rsp+120h+var_E8], 0
0x18002ae52  mov     [rsp+120h+var_F0], 0
0x18002ae5b  mov     [rbp+20h+arg_18], 0
0x18002ae63  mov     [rbp+20h+arg_8], 0
0x18002ae6a  mov     rcx, [rcx]
0x18002ae6d  xorps   xmm7, xmm7
0x18002ae70  xor     eax, eax
0x18002ae72  movq    xmm6, rax
0x18002ae77  xorps   xmm5, xmm5
0x18002ae7a  movq    xmm4, rax
0x18002ae7f  xorps   xmm3, xmm3
0x18002ae82  movq    xmm2, rax
0x18002ae87  xorps   xmm1, xmm1
0x18002ae8a  movaps  xmmword ptr [rsp+120h+pvarg+8], xmm7
0x18002ae8f  movsd   [rsp+120h+var_C0], xmm6
0x18002ae95  movaps  [rbp+20h+var_80], xmm5
0x18002ae99  movsd   [rbp+20h+var_70], xmm4
0x18002ae9e  movaps  [rbp+20h+var_60], xmm3
0x18002aea2  movsd   [rbp+20h+var_50], xmm2
0x18002aea7  movaps  [rbp+20h+var_A0], xmm1
0x18002aeab  mov     [rbp+20h+var_90], rax
0x18002aeaf  mov     rax, [rcx]
0x18002aeb2  lea     rdx, [rsp+120h+pvarg+8]
0x18002aeb7  mov     [rsp+120h+var_100], rdx
0x18002aebc  lea     r9, [rbp+20h+var_80]
0x18002aec0  lea     r8, [rbp+20h+var_60]
0x18002aec4  lea     rdx, [rbp+20h+var_A0]
0x18002aec8  mov     rax, [rax+50h]
0x18002aecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aed1  mov     ebx, eax
0x18002aed3  test    eax, eax
0x18002aed5  jns     short loc_18002AEE0
0x18002aed7  lea     rcx, aTaskserviceCon; "taskService->Connect({}, {}, {}, {})"
0x18002aede  jmp     short loc_18002AF18
0x18002aee0  mov     rdi, [rsi]
0x18002aee3  mov     rax, [rdi]
0x18002aee6  mov     rbx, [rax+38h]
0x18002aeea  lea     rcx, [rsp+120h+var_E8]
0x18002aeef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002aef4  lea     r8, [rsp+120h+var_E8]
0x18002aef9  lea     rdx, asc_18004AA98; "\\"
0x18002af00  mov     rcx, rdi
0x18002af03  mov     rax, rbx
0x18002af06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af0b  mov     ebx, eax
0x18002af0d  test    eax, eax
0x18002af0f  jns     short loc_18002AF24
0x18002af11  lea     rcx, aTaskserviceGet_1; "taskService->GetFolder(L\"\\\\\", &fold"...
0x18002af18  mov     edx, eax
0x18002af1a  call    LogOpFailure
0x18002af1f  jmp     loc_18002B12F
0x18002af24  mov     rbx, [rsi]
0x18002af27  mov     rax, [rbx]
0x18002af2a  mov     rdi, [rax+38h]
0x18002af2e  lea     rcx, [rsp+120h+var_F0]
0x18002af33  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002af38  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\NaturalAuthentica"...
0x18002af3f  lea     rcx, [rbp+20h+arg_10]; this
0x18002af43  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002af48  nop
0x18002af49  mov     rdx, [rax]
0x18002af4c  test    rdx, rdx
0x18002af4f  jz      short loc_18002AF54
0x18002af51  mov     rdx, [rdx]
0x18002af54  lea     r8, [rsp+120h+var_F0]
0x18002af59  mov     rcx, rbx
0x18002af5c  mov     rax, rdi
0x18002af5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af64  mov     ebx, eax
0x18002af66  lea     rcx, [rbp+20h+arg_10]; this
0x18002af6a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002af6f  test    ebx, ebx
0x18002af71  jns     short loc_18002AF7E
0x18002af73  mov     edx, ebx
0x18002af75  lea     rcx, aTaskserviceGet_0; "taskService->GetFolder(_bstr_t(NA_TASK_"...
0x18002af7c  jmp     short loc_18002AF1A
0x18002af7e  mov     rdi, [rsp+120h+var_F0]
0x18002af83  mov     rax, [rdi]
0x18002af86  mov     rbx, [rax+70h]
0x18002af8a  lea     rcx, [rbp+20h+arg_18]
0x18002af8e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002af93  lea     r8, [rbp+20h+arg_18]
0x18002af97  mov     edx, 1
0x18002af9c  mov     rcx, rdi
0x18002af9f  mov     rax, rbx
0x18002afa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afa7  mov     ebx, eax
0x18002afa9  test    eax, eax
0x18002afab  jns     short loc_18002AFB9
0x18002afad  lea     rcx, aSubfolderGetta; "subFolder->GetTasks(TASK_ENUM_HIDDEN, &"...
0x18002afb4  jmp     loc_18002AF18
0x18002afb9  mov     rcx, [rbp+20h+arg_18]
0x18002afbd  mov     rax, [rcx]
0x18002afc0  lea     rdx, [rbp+20h+arg_8]
0x18002afc4  mov     rax, [rax+38h]
0x18002afc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afcd  mov     ebx, eax
0x18002afcf  test    eax, eax
0x18002afd1  jns     short loc_18002AFDF
0x18002afd3  lea     rcx, aTasksGetCountT; "tasks->get_Count(&taskCount)"
0x18002afda  jmp     loc_18002AF18
0x18002afdf  cmp     [rbp+20h+arg_8], 0
0x18002afe3  jz      loc_18002B0D8
0x18002afe9  mov     [rbp+20h+arg_10], 0
0x18002aff1  mov     rdi, [rbp+20h+arg_18]
0x18002aff5  mov     rbx, [rdi]
0x18002aff8  lea     rcx, [rbp+20h+arg_10]
0x18002affc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b001  mov     eax, 3
0x18002b006  mov     word ptr [rsp+120h+pvarg+8], ax
0x18002b00b  mov     edx, [rbp+20h+arg_8]
0x18002b00e  mov     word ptr [rsp+120h+pvarg+10h], dx
0x18002b013  sar     edx, 10h
0x18002b016  mov     word ptr [rsp+120h+pvarg+12h], dx
0x18002b01b  movups  xmm0, xmmword ptr [rsp+120h+pvarg+8]
0x18002b020  movaps  [rbp+20h+var_A0], xmm0
0x18002b024  movsd   xmm1, [rsp+120h+var_C0]
0x18002b02a  movsd   [rbp+20h+var_90], xmm1
0x18002b02f  lea     r8, [rbp+20h+arg_10]
0x18002b033  lea     rdx, [rbp+20h+var_A0]
0x18002b037  mov     rcx, rdi
0x18002b03a  mov     rax, [rbx+40h]
0x18002b03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b043  mov     ebx, eax
0x18002b045  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x18002b04a  call    cs:__imp_VariantClear
0x18002b050  test    ebx, ebx
0x18002b052  js      short loc_18002B0BE
0x18002b054  mov     [rsp+120h+var_E0], 0
0x18002b05d  mov     rcx, [rbp+20h+arg_10]
0x18002b061  mov     rax, [rcx]
0x18002b064  lea     rdx, [rsp+120h+var_E0]
0x18002b069  mov     rax, [rax+38h]
0x18002b06d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b072  mov     ebx, eax
0x18002b074  test    eax, eax
0x18002b076  js      short loc_18002B0B3
0x18002b078  mov     rcx, [rsp+120h+var_F0]
0x18002b07d  mov     rax, [rcx]
0x18002b080  xor     r8d, r8d
0x18002b083  mov     rdx, [rsp+120h+var_E0]
0x18002b088  mov     rax, [rax+78h]
0x18002b08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b091  mov     ebx, eax
0x18002b093  test    eax, eax
0x18002b095  js      short loc_18002B0A8
0x18002b097  dec     [rbp+20h+arg_8]
0x18002b09a  lea     rcx, [rbp+20h+arg_10]
0x18002b09e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b0a3  jmp     loc_18002AFDF
0x18002b0a8  mov     edx, eax
0x18002b0aa  lea     rcx, aSubfolderDelet; "subFolder->DeleteTask(name, 0)"
0x18002b0b1  jmp     short loc_18002B0C7
0x18002b0b3  mov     edx, eax
0x18002b0b5  lea     rcx, aTaskGetNameNam; "task->get_Name(&name)"
0x18002b0bc  jmp     short loc_18002B0C7
0x18002b0be  mov     edx, ebx
0x18002b0c0  lea     rcx, aTasksGetItemVa; "tasks->get_Item(_variant_t(taskCount), "...
0x18002b0c7  call    LogOpFailure
0x18002b0cc  nop
0x18002b0cd  lea     rcx, [rbp+20h+arg_10]
0x18002b0d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b0d6  jmp     short loc_18002B12F
0x18002b0d8  mov     rbx, [rsp+120h+var_E8]
0x18002b0dd  mov     rax, [rbx]
0x18002b0e0  mov     rdi, [rax+60h]
0x18002b0e4  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\NaturalAuthentica"...
0x18002b0eb  lea     rcx, [rsp+120h+var_B0]; this
0x18002b0f0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002b0f5  nop
0x18002b0f6  mov     rdx, [rax]
0x18002b0f9  test    rdx, rdx
0x18002b0fc  jz      short loc_18002B101
0x18002b0fe  mov     rdx, [rdx]
0x18002b101  xor     r8d, r8d
0x18002b104  mov     rcx, rbx
0x18002b107  mov     rax, rdi
0x18002b10a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b10f  mov     ebx, eax
0x18002b111  lea     rcx, [rsp+120h+var_B0]; this
0x18002b116  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002b11b  test    ebx, ebx
0x18002b11d  jns     short loc_18002B12D
0x18002b11f  mov     edx, ebx
0x18002b121  lea     rcx, aFolderDeletefo; "folder->DeleteFolder(_bstr_t(NA_TASK_FO"...
0x18002b128  jmp     loc_18002AF1A
0x18002b12d  xor     ebx, ebx
0x18002b12f  lea     rcx, [rbp+20h+arg_18]
0x18002b133  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b138  nop
0x18002b139  lea     rcx, [rsp+120h+var_F0]
0x18002b13e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b143  nop
0x18002b144  lea     rcx, [rsp+120h+var_E8]
0x18002b149  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b14e  nop
0x18002b14f  mov     rcx, rsi
0x18002b152  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b157  mov     eax, ebx
0x18002b159  lea     r11, [rsp+120h+var_18]
0x18002b161  movaps  xmm6, xmmword ptr [r11-18h]
0x18002b166  movaps  xmm7, xmmword ptr [r11-28h]
0x18002b16b  mov     rsp, r11
0x18002b16e  pop     rdi
0x18002b16f  pop     rsi
0x18002b170  pop     rbx
0x18002b171  pop     rbp
0x18002b172  retn
```
