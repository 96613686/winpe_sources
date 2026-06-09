# std::_Ref_count_obj2<Print::Driver::PrinterExtensionRegistrarService>::_Ref_count_obj2<Print::Driver::PrinterExtensionRegistrarService>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18007e7cc`
- end: `0x18007e8e6`
- name: `??$?0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Ref_count_obj2@VPrinterExtensionRegistrarService@Driver@Print@@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `282`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180081f44`

## callees

- `0x18003fb04`
- `0x18007e7cc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007e84f`
- `KERNEL32!CloseHandle` at `0x18007e87a`
- `KERNEL32!CloseHandle` at `0x18007e8a5`
- `KERNEL32!CloseHandle` at `0x18007e8d0`
- `KERNEL32!CloseHandle` at `0x18007e84f`
- `KERNEL32!CloseHandle` at `0x18007e87a`
- `KERNEL32!CloseHandle` at `0x18007e8a5`
- `KERNEL32!CloseHandle` at `0x18007e8d0`
- `KERNEL32!CreateEventW` at `0x18007e838`
- `KERNEL32!CreateEventW` at `0x18007e863`
- `KERNEL32!CreateEventW` at `0x18007e88e`
- `KERNEL32!CreateEventW` at `0x18007e8b9`
- `KERNEL32!CreateEventW` at `0x18007e838`
- `KERNEL32!CreateEventW` at `0x18007e863`
- `KERNEL32!CreateEventW` at `0x18007e88e`
- `KERNEL32!CreateEventW` at `0x18007e8b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=29 #try_helpers=1
__int64 __fastcall std::_Ref_count_obj2<Print::Driver::PrinterExtensionRegistrarService>::_Ref_count_obj2<Print::Driver::PrinterExtensionRegistrarService>(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v3; // rbx
  HANDLE EventW; // rdi
  char *v5; // rcx
  HANDLE v6; // rdi
  char *v7; // rcx
  HANDLE v8; // rdi
  char *v9; // rcx
  HANDLE v10; // rdi
  char *v11; // rcx

  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &std::_Ref_count_obj2<Print::Driver::PrinterExtensionRegistrarService>::`vftable';
  v3 = (_QWORD *)(a1 + 16);
  *(_OWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 7;
  *(_WORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  std::wstring::operator=(a1 + 16, a2);
  EventW = CreateEventW(0, 1, 0, 0);
  v5 = (char *)v3[4];
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  v3[4] = EventW;
  v6 = CreateEventW(0, 1, 0, 0);
  v7 = (char *)v3[5];
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  v3[5] = v6;
  v8 = CreateEventW(0, 1, 0, 0);
  v9 = (char *)v3[6];
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  v3[6] = v8;
  v10 = CreateEventW(0, 1, 0, 0);
  v11 = (char *)v3[7];
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v11);
  v3[7] = v10;
  return a1;
}

```

## disassembly

```asm
0x18007e7cc  push    rbx
0x18007e7ce  push    rbp
0x18007e7cf  push    rsi
0x18007e7d0  push    rdi
0x18007e7d1  sub     rsp, 38h
0x18007e7d5  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18007e7de  mov     rsi, rcx
0x18007e7e1  mov     ebp, 1
0x18007e7e6  mov     [rcx+8], ebp
0x18007e7e9  mov     [rcx+0Ch], ebp
0x18007e7ec  lea     rax, ??_7?$_Ref_count_obj2@VPrinterExtensionRegistrarService@Driver@Print@@@std@@6B@; const std::_Ref_count_obj2<Print::Driver::PrinterExtensionRegistrarService>::`vftable'
0x18007e7f3  mov     [rcx], rax
0x18007e7f6  lea     rbx, [rcx+10h]
0x18007e7fa  mov     [rsp+58h+arg_0], rbx
0x18007e7ff  xorps   xmm0, xmm0
0x18007e802  movups  xmmword ptr [rbx], xmm0
0x18007e805  xor     ecx, ecx
0x18007e807  mov     [rbx+10h], rcx
0x18007e80b  mov     qword ptr [rbx+18h], 7
0x18007e813  mov     [rbx], cx
0x18007e816  mov     [rbx+20h], rcx
0x18007e81a  mov     [rbx+28h], rcx
0x18007e81e  mov     [rbx+30h], rcx
0x18007e822  mov     [rbx+38h], rcx
0x18007e826  mov     rcx, rbx
0x18007e829  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007e82e  xor     r9d, r9d; lpName
0x18007e831  xor     r8d, r8d; bInitialState
0x18007e834  mov     edx, ebp; bManualReset
0x18007e836  xor     ecx, ecx; lpEventAttributes
0x18007e838  call    cs:__imp_CreateEventW
0x18007e83e  mov     rdi, rax
0x18007e841  mov     rcx, [rbx+20h]; hObject
0x18007e845  lea     rdx, [rcx-1]
0x18007e849  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18007e84d  ja      short loc_18007E855
0x18007e84f  call    cs:__imp_CloseHandle
0x18007e855  mov     [rbx+20h], rdi
0x18007e859  xor     r9d, r9d; lpName
0x18007e85c  xor     r8d, r8d; bInitialState
0x18007e85f  mov     edx, ebp; bManualReset
0x18007e861  xor     ecx, ecx; lpEventAttributes
0x18007e863  call    cs:__imp_CreateEventW
0x18007e869  mov     rdi, rax
0x18007e86c  mov     rcx, [rbx+28h]; hObject
0x18007e870  lea     rdx, [rcx-1]
0x18007e874  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18007e878  ja      short loc_18007E880
0x18007e87a  call    cs:__imp_CloseHandle
0x18007e880  mov     [rbx+28h], rdi
0x18007e884  xor     r9d, r9d; lpName
0x18007e887  xor     r8d, r8d; bInitialState
0x18007e88a  mov     edx, ebp; bManualReset
0x18007e88c  xor     ecx, ecx; lpEventAttributes
0x18007e88e  call    cs:__imp_CreateEventW
0x18007e894  mov     rdi, rax
0x18007e897  mov     rcx, [rbx+30h]; hObject
0x18007e89b  lea     r8, [rcx-1]
0x18007e89f  cmp     r8, 0FFFFFFFFFFFFFFFDh
0x18007e8a3  ja      short loc_18007E8AB
0x18007e8a5  call    cs:__imp_CloseHandle
0x18007e8ab  mov     [rbx+30h], rdi
0x18007e8af  xor     r9d, r9d; lpName
0x18007e8b2  xor     r8d, r8d; bInitialState
0x18007e8b5  mov     edx, ebp; bManualReset
0x18007e8b7  xor     ecx, ecx; lpEventAttributes
0x18007e8b9  call    cs:__imp_CreateEventW
0x18007e8bf  mov     rdi, rax
0x18007e8c2  mov     rcx, [rbx+38h]; hObject
0x18007e8c6  lea     rdx, [rcx-1]
0x18007e8ca  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18007e8ce  ja      short loc_18007E8D6
0x18007e8d0  call    cs:__imp_CloseHandle
0x18007e8d6  mov     [rbx+38h], rdi
0x18007e8da  mov     rax, rsi
0x18007e8dd  add     rsp, 38h
0x18007e8e1  pop     rdi
0x18007e8e2  pop     rsi
0x18007e8e3  pop     rbp
0x18007e8e4  pop     rbx
0x18007e8e5  retn
```
