# CreateAggregateOLITEMIDFromContactId(ulong,OLITEMID *)

- ea: `0x18000d578`
- end: `0x18000d634`
- name: `?CreateAggregateOLITEMIDFromContactId@@YAJKPEAUOLITEMID@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(int, struct OLITEMID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001cf00`

## callees

- `0x18000428c`
- `0x18000d578`
- `0x18000db08`
- `0x180021240`
- `0x180022010`

## import_xrefs

- `unistore!CreateStoreManager` at `0x18000d5aa`
- `unistore!CreateStoreManager` at `0x18000d5aa`

## pseudocode

```c
__int64 __fastcall CreateAggregateOLITEMIDFromContactId(int a1, struct OLITEMID *a2)
{
  int v4; // eax
  __int64 v5; // r8
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v9; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+38h] [rbp-20h] BYREF
  int v11; // [rsp+40h] [rbp-18h]

  v9 = 0;
  v4 = CreateStoreManager(0, &v9);
  v6 = v4;
  if ( v4 >= 0 )
  {
    v10 = 0;
    v11 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 56LL))(v9, &v10);
    v6 = v4;
    if ( v4 >= 0 )
    {
      v6 = 0;
      *(_DWORD *)a2 = v10;
      *((_DWORD *)a2 + 1) = 458754;
      *((_DWORD *)a2 + 2) = a1;
      goto LABEL_7;
    }
    v7 = 174;
  }
  else
  {
    v7 = 171;
  }
  Log_HREvent_1((unsigned int)v4, 1, v5, v7);
LABEL_7:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  return v6;
}

```

## disassembly

```asm
0x18000d578  mov     r11, rsp
0x18000d57b  mov     [r11+8], rbx
0x18000d57f  mov     [r11+18h], rsi
0x18000d583  push    rdi
0x18000d584  sub     rsp, 50h
0x18000d588  mov     rax, cs:__security_cookie
0x18000d58f  xor     rax, rsp
0x18000d592  mov     [rsp+58h+var_10], rax
0x18000d597  mov     rdi, rdx
0x18000d59a  mov     qword ptr [r11-28h], 0
0x18000d5a2  mov     esi, ecx
0x18000d5a4  lea     rdx, [r11-28h]
0x18000d5a8  xor     ecx, ecx
0x18000d5aa  call    cs:__imp_CreateStoreManager
0x18000d5b0  mov     ebx, eax
0x18000d5b2  test    eax, eax
0x18000d5b4  jns     short loc_18000D5BE
0x18000d5b6  mov     r9d, 0ABh
0x18000d5bc  jmp     short loc_18000D5EB
0x18000d5be  mov     rcx, [rsp+58h+var_28]
0x18000d5c3  lea     rdx, [rsp+58h+var_20]
0x18000d5c8  xor     eax, eax
0x18000d5ca  mov     [rsp+58h+var_20], rax
0x18000d5cf  mov     [rsp+58h+var_18], eax
0x18000d5d3  mov     rax, [rcx]
0x18000d5d6  mov     rax, [rax+38h]
0x18000d5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5df  mov     ebx, eax
0x18000d5e1  test    eax, eax
0x18000d5e3  jns     short loc_18000D5F9
0x18000d5e5  mov     r9d, 0AEh
0x18000d5eb  mov     edx, 1
0x18000d5f0  mov     ecx, eax
0x18000d5f2  call    Log_HREvent_1
0x18000d5f7  jmp     short loc_18000D60B
0x18000d5f9  mov     eax, dword ptr [rsp+58h+var_20]
0x18000d5fd  xor     ebx, ebx
0x18000d5ff  mov     [rdi], eax
0x18000d601  mov     dword ptr [rdi+4], 70002h
0x18000d608  mov     [rdi+8], esi
0x18000d60b  lea     rcx, [rsp+58h+var_28]
0x18000d610  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d615  mov     eax, ebx
0x18000d617  mov     rcx, [rsp+58h+var_10]
0x18000d61c  xor     rcx, rsp; StackCookie
0x18000d61f  call    __security_check_cookie
0x18000d624  mov     rbx, [rsp+58h+arg_0]
0x18000d629  mov     rsi, [rsp+58h+arg_10]
0x18000d62e  add     rsp, 50h
0x18000d632  pop     rdi
0x18000d633  retn
```
