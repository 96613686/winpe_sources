# ATL::CAtlDllModuleT<CPenImcModule>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180001798`
- end: `0x1800018f7`
- name: `?DllGetClassObject@?$CAtlDllModuleT@VCPenImcModule@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800014a0`

## callees

- `0x180001798`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x1800018af`
- `KERNEL32!DecodePointer` at `0x1800018af`
- `KERNEL32!EncodePointer` at `0x180001890`
- `KERNEL32!EncodePointer` at `0x180001890`
- `KERNEL32!EnterCriticalSection` at `0x180001854`
- `KERNEL32!EnterCriticalSection` at `0x180001854`
- `KERNEL32!LeaveCriticalSection` at `0x18000189c`
- `KERNEL32!LeaveCriticalSection` at `0x18000189c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAtlDllModuleT<CPenImcModule>::DllGetClassObject(void *a1, _DWORD *a2, __int64 a3, _QWORD *a4)
{
  int v7; // ebx
  GUID **i; // rcx
  GUID *v9; // rsi
  _DWORD *v10; // rdx
  void **v11; // rdi
  void *v12; // rcx
  __int64 (__fastcall ***v13)(PVOID, __int64, _QWORD *); // rax
  PVOID Ptr; // [rsp+50h] [rbp+8h] BYREF

  Ptr = a1;
  if ( a4 )
  {
    *a4 = 0;
    if ( ATL::_AtlComModule )
    {
      v7 = 0;
      for ( i = off_180018210; i < (GUID **)off_180018218; ++i )
      {
        v9 = *i;
        if ( *i )
        {
          if ( *(_QWORD *)&v9[1].Data1 )
          {
            v10 = *(_DWORD **)&v9->Data1;
            if ( *a2 == **(_DWORD **)&v9->Data1 && a2[1] == v10[1] && a2[2] == v10[2] && a2[3] == v10[3] )
            {
              v11 = *(void ***)&v9[2].Data1;
              v12 = *v11;
              if ( *v11 )
                goto LABEL_19;
              EnterCriticalSection(&stru_180018220);
              v7 = 0;
              if ( !*v11 )
              {
                Ptr = 0;
                v7 = (*(__int64 (__fastcall **)(_QWORD, GUID *, PVOID *))&v9[1].Data1)(
                       *(_QWORD *)v9[1].Data4,
                       &GUID_00000000_0000_0000_c000_000000000046,
                       &Ptr);
                if ( v7 >= 0 )
                  *v11 = EncodePointer(Ptr);
              }
              LeaveCriticalSection(&stru_180018220);
              v12 = *v11;
              if ( *v11 )
              {
LABEL_19:
                v13 = (__int64 (__fastcall ***)(PVOID, __int64, _QWORD *))DecodePointer(v12);
                v7 = (**v13)(v13, a3, a4);
              }
              break;
            }
          }
        }
      }
      if ( !*a4 && !v7 )
        return (unsigned int)-2147221231;
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180001798  mov     rax, rsp
0x18000179b  mov     [rax+10h], rbx
0x18000179f  mov     [rax+18h], rbp
0x1800017a3  mov     [rax+20h], rsi
0x1800017a7  mov     [rax+8], rcx
0x1800017ab  push    rdi
0x1800017ac  push    r12
0x1800017ae  push    r14
0x1800017b0  sub     rsp, 30h
0x1800017b4  mov     r14, r9
0x1800017b7  mov     rbp, r8
0x1800017ba  mov     r9, rdx
0x1800017bd  test    r14, r14
0x1800017c0  jnz     short loc_1800017CC
0x1800017c2  mov     ebx, 80004003h
0x1800017c7  jmp     loc_1800018DC
0x1800017cc  and     qword ptr [r14], 0
0x1800017d0  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800017d7  jnz     short loc_1800017E3
0x1800017d9  mov     ebx, 8000FFFFh
0x1800017de  jmp     loc_1800018DC
0x1800017e3  xor     ebx, ebx
0x1800017e5  mov     rcx, cs:off_180018210
0x1800017ec  mov     r8, cs:off_180018218
0x1800017f3  cmp     rcx, r8
0x1800017f6  jnb     loc_1800018CC
0x1800017fc  mov     rsi, [rcx]
0x1800017ff  test    rsi, rsi
0x180001802  jz      short loc_18000182F
0x180001804  cmp     [rsi+10h], rbx
0x180001808  jz      short loc_18000182F
0x18000180a  mov     rdx, [rsi]
0x18000180d  mov     eax, [rdx]
0x18000180f  cmp     [r9], eax
0x180001812  jnz     short loc_18000182F
0x180001814  mov     eax, [rdx+4]
0x180001817  cmp     [r9+4], eax
0x18000181b  jnz     short loc_18000182F
0x18000181d  mov     eax, [rdx+8]
0x180001820  cmp     [r9+8], eax
0x180001824  jnz     short loc_18000182F
0x180001826  mov     eax, [rdx+0Ch]
0x180001829  cmp     [r9+0Ch], eax
0x18000182d  jz      short loc_180001835
0x18000182f  add     rcx, 8
0x180001833  jmp     short loc_1800017F3
0x180001835  mov     rdi, [rsi+20h]
0x180001839  mov     rcx, [rdi]
0x18000183c  test    rcx, rcx
0x18000183f  jnz     short loc_1800018AF
0x180001841  lea     r12, stru_180018220
0x180001848  mov     [rsp+48h+var_28], r12
0x18000184d  mov     [rsp+48h+var_20], bl
0x180001851  mov     rcx, r12; lpCriticalSection
0x180001854  call    cs:__imp_EnterCriticalSection
0x18000185a  mov     [rsp+48h+var_20], 1
0x18000185f  xor     ebx, ebx
0x180001861  cmp     [rdi], rbx
0x180001864  jnz     short loc_180001899
0x180001866  and     [rsp+48h+Ptr], rbx
0x18000186b  lea     r8, [rsp+48h+Ptr]
0x180001870  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180001877  mov     rcx, [rsi+18h]
0x18000187b  mov     rax, [rsi+10h]
0x18000187f  call    cs:__guard_dispatch_icall_fptr
0x180001885  mov     ebx, eax
0x180001887  test    eax, eax
0x180001889  js      short loc_180001899
0x18000188b  mov     rcx, [rsp+48h+Ptr]; Ptr
0x180001890  call    cs:__imp_EncodePointer
0x180001896  mov     [rdi], rax
0x180001899  mov     rcx, r12; lpCriticalSection
0x18000189c  call    cs:__imp_LeaveCriticalSection
0x1800018a2  mov     [rsp+48h+var_20], 0
0x1800018a7  mov     rcx, [rdi]; Ptr
0x1800018aa  test    rcx, rcx
0x1800018ad  jz      short loc_1800018CC
0x1800018af  call    cs:__imp_DecodePointer
0x1800018b5  mov     rcx, rax
0x1800018b8  mov     rax, [rax]
0x1800018bb  mov     r8, r14
0x1800018be  mov     rdx, rbp
0x1800018c1  mov     rax, [rax]
0x1800018c4  call    cs:__guard_dispatch_icall_fptr
0x1800018ca  mov     ebx, eax
0x1800018cc  cmp     qword ptr [r14], 0
0x1800018d0  jnz     short loc_1800018DC
0x1800018d2  mov     eax, 80040111h
0x1800018d7  test    ebx, ebx
0x1800018d9  cmovz   ebx, eax
0x1800018dc  mov     eax, ebx
0x1800018de  mov     rbx, [rsp+48h+arg_8]
0x1800018e3  mov     rbp, [rsp+48h+arg_10]
0x1800018e8  mov     rsi, [rsp+48h+arg_18]
0x1800018ed  add     rsp, 30h
0x1800018f1  pop     r14
0x1800018f3  pop     r12
0x1800018f5  pop     rdi
0x1800018f6  retn
```
