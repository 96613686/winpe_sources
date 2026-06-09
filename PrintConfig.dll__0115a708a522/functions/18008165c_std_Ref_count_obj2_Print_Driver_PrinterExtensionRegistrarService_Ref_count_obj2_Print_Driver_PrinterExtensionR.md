# std::_Ref_count_obj2<Print::Driver::PrinterExtensionRegistrarService>::_Ref_count_obj2<Print::Driver::PrinterExtensionRegistrarService>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18008165c`
- end: `0x1800817a7`
- name: `??$?0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Ref_count_obj2@VPrinterExtensionRegistrarService@Driver@Print@@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `331`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180084fec`

## callees

- `0x1800412a4`
- `0x18008165c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800816e5`
- `KERNEL32!CloseHandle` at `0x18008171c`
- `KERNEL32!CloseHandle` at `0x180081753`
- `KERNEL32!CloseHandle` at `0x18008178a`
- `KERNEL32!CloseHandle` at `0x1800816e5`
- `KERNEL32!CloseHandle` at `0x18008171c`
- `KERNEL32!CloseHandle` at `0x180081753`
- `KERNEL32!CloseHandle` at `0x18008178a`
- `KERNEL32!CreateEventW` at `0x1800816c8`
- `KERNEL32!CreateEventW` at `0x1800816ff`
- `KERNEL32!CreateEventW` at `0x180081736`
- `KERNEL32!CreateEventW` at `0x18008176d`
- `KERNEL32!CreateEventW` at `0x1800816c8`
- `KERNEL32!CreateEventW` at `0x1800816ff`
- `KERNEL32!CreateEventW` at `0x180081736`
- `KERNEL32!CreateEventW` at `0x18008176d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall std::_Ref_count_obj2<Print::Driver::PrinterExtensionRegistrarService>::_Ref_count_obj2<Print::Driver::PrinterExtensionRegistrarService>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  _QWORD *v4; // rbx
  HANDLE EventW; // rdi
  char *v6; // rcx
  HANDLE v7; // rdi
  char *v8; // rcx
  HANDLE v9; // rdi
  char *v10; // rcx
  HANDLE v11; // rdi
  char *v12; // rcx

  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &std::_Ref_count_obj2<Print::Driver::PrinterExtensionRegistrarService>::`vftable';
  v4 = (_QWORD *)(a1 + 16);
  *(_OWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 7;
  *(_WORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  std::wstring::operator=(a1 + 16, a2, a3);
  EventW = CreateEventW(0, 1, 0, 0);
  v6 = (char *)v4[4];
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  v4[4] = EventW;
  v7 = CreateEventW(0, 1, 0, 0);
  v8 = (char *)v4[5];
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  v4[5] = v7;
  v9 = CreateEventW(0, 1, 0, 0);
  v10 = (char *)v4[6];
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v10);
  v4[6] = v9;
  v11 = CreateEventW(0, 1, 0, 0);
  v12 = (char *)v4[7];
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v12);
  v4[7] = v11;
  return a1;
}

```

## disassembly

```asm
0x18008165c  push    rbx
0x18008165e  push    rbp
0x18008165f  push    rsi
0x180081660  push    rdi
0x180081661  sub     rsp, 38h
0x180081665  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18008166e  mov     rsi, rcx
0x180081671  mov     ebp, 1
0x180081676  mov     [rcx+8], ebp
0x180081679  mov     [rcx+0Ch], ebp
0x18008167c  lea     rax, ??_7?$_Ref_count_obj2@VPrinterExtensionRegistrarService@Driver@Print@@@std@@6B@; const std::_Ref_count_obj2<Print::Driver::PrinterExtensionRegistrarService>::`vftable'
0x180081683  mov     [rcx], rax
0x180081686  lea     rbx, [rcx+10h]
0x18008168a  mov     [rsp+58h+arg_0], rbx
0x18008168f  xorps   xmm0, xmm0
0x180081692  movups  xmmword ptr [rbx], xmm0
0x180081695  xor     ecx, ecx
0x180081697  mov     [rbx+10h], rcx
0x18008169b  mov     qword ptr [rbx+18h], 7
0x1800816a3  mov     [rbx], cx
0x1800816a6  mov     [rbx+20h], rcx
0x1800816aa  mov     [rbx+28h], rcx
0x1800816ae  mov     [rbx+30h], rcx
0x1800816b2  mov     [rbx+38h], rcx
0x1800816b6  mov     rcx, rbx
0x1800816b9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800816be  xor     r9d, r9d; lpName
0x1800816c1  xor     r8d, r8d; bInitialState
0x1800816c4  mov     edx, ebp; bManualReset
0x1800816c6  xor     ecx, ecx; lpEventAttributes
0x1800816c8  call    cs:__imp_CreateEventW
0x1800816cf  nop     dword ptr [rax+rax+00h]
0x1800816d4  mov     rdi, rax
0x1800816d7  mov     rcx, [rbx+20h]; hObject
0x1800816db  lea     rdx, [rcx-1]
0x1800816df  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800816e3  ja      short loc_1800816F1
0x1800816e5  call    cs:__imp_CloseHandle
0x1800816ec  nop     dword ptr [rax+rax+00h]
0x1800816f1  mov     [rbx+20h], rdi
0x1800816f5  xor     r9d, r9d; lpName
0x1800816f8  xor     r8d, r8d; bInitialState
0x1800816fb  mov     edx, ebp; bManualReset
0x1800816fd  xor     ecx, ecx; lpEventAttributes
0x1800816ff  call    cs:__imp_CreateEventW
0x180081706  nop     dword ptr [rax+rax+00h]
0x18008170b  mov     rdi, rax
0x18008170e  mov     rcx, [rbx+28h]; hObject
0x180081712  lea     rdx, [rcx-1]
0x180081716  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18008171a  ja      short loc_180081728
0x18008171c  call    cs:__imp_CloseHandle
0x180081723  nop     dword ptr [rax+rax+00h]
0x180081728  mov     [rbx+28h], rdi
0x18008172c  xor     r9d, r9d; lpName
0x18008172f  xor     r8d, r8d; bInitialState
0x180081732  mov     edx, ebp; bManualReset
0x180081734  xor     ecx, ecx; lpEventAttributes
0x180081736  call    cs:__imp_CreateEventW
0x18008173d  nop     dword ptr [rax+rax+00h]
0x180081742  mov     rdi, rax
0x180081745  mov     rcx, [rbx+30h]; hObject
0x180081749  lea     r8, [rcx-1]
0x18008174d  cmp     r8, 0FFFFFFFFFFFFFFFDh
0x180081751  ja      short loc_18008175F
0x180081753  call    cs:__imp_CloseHandle
0x18008175a  nop     dword ptr [rax+rax+00h]
0x18008175f  mov     [rbx+30h], rdi
0x180081763  xor     r9d, r9d; lpName
0x180081766  xor     r8d, r8d; bInitialState
0x180081769  mov     edx, ebp; bManualReset
0x18008176b  xor     ecx, ecx; lpEventAttributes
0x18008176d  call    cs:__imp_CreateEventW
0x180081774  nop     dword ptr [rax+rax+00h]
0x180081779  mov     rdi, rax
0x18008177c  mov     rcx, [rbx+38h]; hObject
0x180081780  lea     rdx, [rcx-1]
0x180081784  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180081788  ja      short loc_180081796
0x18008178a  call    cs:__imp_CloseHandle
0x180081791  nop     dword ptr [rax+rax+00h]
0x180081796  mov     [rbx+38h], rdi
0x18008179a  mov     rax, rsi
0x18008179d  add     rsp, 38h
0x1800817a1  pop     rdi
0x1800817a2  pop     rsi
0x1800817a3  pop     rbp
0x1800817a4  pop     rbx
0x1800817a5  retn
```
