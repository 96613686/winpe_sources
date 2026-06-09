# IsNetworkCategoryQualified(NLM_NETWORK_CATEGORY,int *,ulong *)

- ea: `0x18000f650`
- end: `0x18000f894`
- name: `?IsNetworkCategoryQualified@@YAJW4NLM_NETWORK_CATEGORY@@PEAHPEAK@Z`
- size: `580`
- prototype: `__int64 __fastcall(enum NLM_NETWORK_CATEGORY, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010120`

## callees

- `0x18000a644`
- `0x18000a778`
- `0x18000f650`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f70d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f70d`

## pseudocode

```c
__int64 __fastcall IsNetworkCategoryQualified(enum NLM_NETWORK_CATEGORY a1, int *a2, unsigned int *a3)
{
  __int64 v4; // rdi
  _QWORD *v6; // r10
  HRESULT v7; // ebx
  __int64 v8; // rdx
  int v9; // edi
  __int64 v10; // rdx
  __int64 v11; // rdx
  int v13; // [rsp+60h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+10h] BYREF

  v4 = a1;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  *a2 = 0;
  *a3 = 4;
  if ( *((_DWORD *)&g_NetworkConfiguration + 4 * v4) )
  {
    ppv = 0;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      WPP_SF_(v6[2], 16, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
    v7 = CoCreateInstance(
           &GUID_1fda955b_61ff_11da_978c_0008744faab7,
           0,
           1u,
           &GUID_1fda955c_61ff_11da_978c_0008744faab7,
           &ppv);
    if ( v7 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v8 = 17;
LABEL_12:
        WPP_SF_d(v6[2], v8, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
LABEL_32:
        v6 = WPP_GLOBAL_Control;
        goto LABEL_33;
      }
      goto LABEL_33;
    }
    v13 = 0;
    if ( (_DWORD)v4 )
    {
      v9 = v4 - 1;
      if ( v9 )
      {
        if ( v9 != 1 )
        {
          v7 = -2147418113;
LABEL_21:
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v8 = 18;
            goto LABEL_12;
          }
LABEL_33:
          if ( ppv )
          {
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_38:
            v6 = WPP_GLOBAL_Control;
            goto LABEL_39;
          }
          goto LABEL_39;
        }
        v10 = 1;
      }
      else
      {
        v10 = 2;
      }
    }
    else
    {
      v10 = 4;
    }
    v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, int *, _QWORD))(*(_QWORD *)ppv + 48LL))(
           ppv,
           v10,
           0,
           &v13,
           0);
    if ( v7 >= 0 )
    {
      if ( v13 )
      {
        *a2 = 1;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_33;
        v11 = 19;
      }
      else
      {
        *a3 = 3;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_33;
        v11 = 20;
      }
      WPP_SF_(v6[2], v11, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
      goto LABEL_32;
    }
    goto LABEL_21;
  }
  v7 = 0;
  *a3 = 1;
  if ( v6 == &WPP_GLOBAL_Control )
    return (unsigned int)v7;
  if ( (*((_BYTE *)v6 + 28) & 8) != 0 )
  {
    WPP_SF_(v6[2], 21, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
    goto LABEL_38;
  }
LABEL_39:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_(v6[2], 22, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f650  mov     [rsp+arg_10], rbx
0x18000f655  push    rdi
0x18000f656  push    r12
0x18000f658  push    r13
0x18000f65a  push    r14
0x18000f65c  push    r15
0x18000f65e  sub     rsp, 30h
0x18000f662  mov     r14, r8
0x18000f665  movsxd  rdi, ecx
0x18000f668  mov     r15, rdx
0x18000f66b  mov     r10, cs:WPP_GLOBAL_Control
0x18000f672  lea     r12, WPP_GLOBAL_Control
0x18000f679  lea     r13, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000f680  cmp     r10, r12
0x18000f683  jz      short loc_18000F6A4
0x18000f685  test    byte ptr [r10+1Ch], 20h
0x18000f68a  jz      short loc_18000F6A4
0x18000f68c  mov     rcx, [r10+10h]
0x18000f690  mov     edx, 0Fh
0x18000f695  mov     r8, r13
0x18000f698  call    WPP_SF_
0x18000f69d  mov     r10, cs:WPP_GLOBAL_Control
0x18000f6a4  mov     rax, rdi
0x18000f6a7  mov     dword ptr [r15], 0
0x18000f6ae  add     rax, rax
0x18000f6b1  mov     dword ptr [r14], 4
0x18000f6b8  lea     rcx, ?g_NetworkConfiguration@@3PAUNETWORK_CONFIGURATION@@A; NETWORK_CONFIGURATION near * g_NetworkConfiguration
0x18000f6bf  cmp     dword ptr [rcx+rax*8], 0
0x18000f6c3  jz      loc_18000F837
0x18000f6c9  mov     [rsp+58h+arg_8], 0
0x18000f6d2  cmp     r10, r12
0x18000f6d5  jz      short loc_18000F6EF
0x18000f6d7  test    byte ptr [r10+1Ch], 8
0x18000f6dc  jz      short loc_18000F6EF
0x18000f6de  mov     rcx, [r10+10h]
0x18000f6e2  mov     edx, 10h
0x18000f6e7  mov     r8, r13
0x18000f6ea  call    WPP_SF_
0x18000f6ef  xor     edx, edx; pUnkOuter
0x18000f6f1  lea     rax, [rsp+58h+arg_8]
0x18000f6f6  lea     r9, _GUID_1fda955c_61ff_11da_978c_0008744faab7; riid
0x18000f6fd  mov     [rsp+58h+ppv], rax; ppv
0x18000f702  lea     rcx, _GUID_1fda955b_61ff_11da_978c_0008744faab7; rclsid
0x18000f709  lea     r8d, [rdx+1]; dwClsContext
0x18000f70d  call    cs:__imp_CoCreateInstance
0x18000f713  mov     ebx, eax
0x18000f715  test    eax, eax
0x18000f717  jns     short loc_18000F74D
0x18000f719  mov     r10, cs:WPP_GLOBAL_Control
0x18000f720  cmp     r10, r12
0x18000f723  jz      loc_18000F81F
0x18000f729  test    byte ptr [r10+1Ch], 2
0x18000f72e  jz      loc_18000F81F
0x18000f734  mov     edx, 11h
0x18000f739  mov     r9d, eax
0x18000f73c  mov     rcx, [r10+10h]
0x18000f740  mov     r8, r13
0x18000f743  call    WPP_SF_d
0x18000f748  jmp     loc_18000F818
0x18000f74d  mov     [rsp+58h+arg_0], 0
0x18000f755  test    edi, edi
0x18000f757  jz      short loc_18000F778
0x18000f759  sub     edi, 1
0x18000f75c  jz      short loc_18000F771
0x18000f75e  cmp     edi, 1
0x18000f761  jz      short loc_18000F76A
0x18000f763  mov     ebx, 8000FFFFh
0x18000f768  jmp     short loc_18000F7A5
0x18000f76a  mov     edx, 1
0x18000f76f  jmp     short loc_18000F77D
0x18000f771  mov     edx, 2
0x18000f776  jmp     short loc_18000F77D
0x18000f778  mov     edx, 4
0x18000f77d  mov     rcx, [rsp+58h+arg_8]
0x18000f782  lea     r9, [rsp+58h+arg_0]
0x18000f787  xor     r8d, r8d
0x18000f78a  mov     [rsp+58h+ppv], 0
0x18000f793  mov     rax, [rcx]
0x18000f796  mov     rax, [rax+30h]
0x18000f79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f79f  mov     ebx, eax
0x18000f7a1  test    eax, eax
0x18000f7a3  jns     short loc_18000F7C5
0x18000f7a5  mov     r10, cs:WPP_GLOBAL_Control
0x18000f7ac  cmp     r10, r12
0x18000f7af  jz      short loc_18000F81F
0x18000f7b1  test    byte ptr [r10+1Ch], 2
0x18000f7b6  jz      short loc_18000F81F
0x18000f7b8  mov     edx, 12h
0x18000f7bd  mov     r9d, ebx
0x18000f7c0  jmp     loc_18000F73C
0x18000f7c5  cmp     [rsp+58h+arg_0], 0
0x18000f7ca  jz      short loc_18000F7ED
0x18000f7cc  mov     dword ptr [r15], 1
0x18000f7d3  mov     r10, cs:WPP_GLOBAL_Control
0x18000f7da  cmp     r10, r12
0x18000f7dd  jz      short loc_18000F81F
0x18000f7df  test    byte ptr [r10+1Ch], 8
0x18000f7e4  jz      short loc_18000F81F
0x18000f7e6  mov     edx, 13h
0x18000f7eb  jmp     short loc_18000F80C
0x18000f7ed  mov     dword ptr [r14], 3
0x18000f7f4  mov     r10, cs:WPP_GLOBAL_Control
0x18000f7fb  cmp     r10, r12
0x18000f7fe  jz      short loc_18000F81F
0x18000f800  test    byte ptr [r10+1Ch], 8
0x18000f805  jz      short loc_18000F81F
0x18000f807  mov     edx, 14h
0x18000f80c  mov     rcx, [r10+10h]
0x18000f810  mov     r8, r13
0x18000f813  call    WPP_SF_
0x18000f818  mov     r10, cs:WPP_GLOBAL_Control
0x18000f81f  mov     rcx, [rsp+58h+arg_8]
0x18000f824  test    rcx, rcx
0x18000f827  jz      short loc_18000F862
0x18000f829  mov     rax, [rcx]
0x18000f82c  mov     rax, [rax+10h]
0x18000f830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f835  jmp     short loc_18000F85B
0x18000f837  xor     ebx, ebx
0x18000f839  mov     dword ptr [r14], 1
0x18000f840  cmp     r10, r12
0x18000f843  jz      short loc_18000F87F
0x18000f845  test    byte ptr [r10+1Ch], 8
0x18000f84a  jz      short loc_18000F862
0x18000f84c  mov     rcx, [r10+10h]
0x18000f850  lea     edx, [rbx+15h]
0x18000f853  mov     r8, r13
0x18000f856  call    WPP_SF_
0x18000f85b  mov     r10, cs:WPP_GLOBAL_Control
0x18000f862  cmp     r10, r12
0x18000f865  jz      short loc_18000F87F
0x18000f867  test    byte ptr [r10+1Ch], 20h
0x18000f86c  jz      short loc_18000F87F
0x18000f86e  mov     rcx, [r10+10h]
0x18000f872  mov     edx, 16h
0x18000f877  mov     r8, r13
0x18000f87a  call    WPP_SF_
0x18000f87f  mov     eax, ebx
0x18000f881  mov     rbx, [rsp+58h+arg_10]
0x18000f886  add     rsp, 30h
0x18000f88a  pop     r15
0x18000f88c  pop     r14
0x18000f88e  pop     r13
0x18000f890  pop     r12
0x18000f892  pop     rdi
0x18000f893  retn
```
