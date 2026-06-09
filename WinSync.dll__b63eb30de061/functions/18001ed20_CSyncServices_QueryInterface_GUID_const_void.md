# CSyncServices::QueryInterface(_GUID const &,void * *)

- ea: `0x18001ed20`
- end: `0x18001ef45`
- name: `?QueryInterface@CSyncServices@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `549`
- prototype: `__int64 __fastcall(CSyncServices *__hidden this, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002d240`
- `0x18002d250`
- `0x18002d260`
- `0x18002d270`
- `0x18002d280`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18001ed20`
- `0x180094010`

## string_xrefs

- `0x18001eed7`: `CSyncServices::QueryInterface`
- `0x18001ef24`: `CSyncServices::QueryInterface`

## pseudocode

```c
__int64 __fastcall CSyncServices::QueryInterface(CSyncServices *this, const struct _GUID *a2, void **a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // esi
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::QueryInterface");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = -2147467261;
  if ( a3 )
  {
    *a3 = 0;
    v7 = -2147467262;
    v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v8 )
    {
      v9 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IApplicationSyncServices.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IApplicationSyncServices.Data1 )
        v9 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IApplicationSyncServices.Data4;
      if ( v9 )
      {
        v10 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IProviderSyncServices.Data1;
        if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IProviderSyncServices.Data1 )
          v10 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IProviderSyncServices.Data4;
        if ( !v10 )
          goto LABEL_13;
        v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IProviderSyncServices2.Data1;
        if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IProviderSyncServices2.Data1 )
          v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IProviderSyncServices2.Data4;
        if ( v13 )
        {
          v14 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IProviderFilteredSyncServices.Data1;
          if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IProviderFilteredSyncServices.Data1 )
            v14 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IProviderFilteredSyncServices.Data4;
          if ( !v14 )
            goto LABEL_42;
          v15 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IProviderFilteredSyncServices2.Data1;
          if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IProviderFilteredSyncServices2.Data1 )
            v15 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IProviderFilteredSyncServices2.Data4;
          if ( v15 )
          {
            v16 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IProviderCustomFilteredSyncServices.Data1;
            if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IProviderCustomFilteredSyncServices.Data1 )
              v16 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IProviderCustomFilteredSyncServices.Data4;
            if ( v16 )
            {
              v17 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IClockVectorServices.Data1;
              if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IClockVectorServices.Data1 )
                v17 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IClockVectorServices.Data4;
              if ( v17 )
              {
                v18 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISupportErrorInfo.Data1;
                if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISupportErrorInfo.Data1 )
                  v18 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISupportErrorInfo.Data4;
                if ( v18 )
                  goto LABEL_17;
                v11 = (unsigned __int64)this + 40;
              }
              else
              {
                v11 = (unsigned __int64)this + 32;
              }
            }
            else
            {
              v11 = (unsigned __int64)this + 24;
            }
          }
          else
          {
LABEL_42:
            v11 = (unsigned __int64)this + 8;
          }
        }
        else
        {
LABEL_13:
          v11 = (unsigned __int64)this + 16;
        }
        this = (CSyncServices *)(v11 & -(__int64)(this != 0));
      }
    }
    if ( this )
    {
      *a3 = this;
      (*(void (__fastcall **)(CSyncServices *))(*(_QWORD *)this + 8LL))(this);
      v7 = 0;
    }
LABEL_17:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      11,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::QueryInterface",
      v7);
  return v7;
}

```

## disassembly

```asm
0x18001ed20  push    rbx
0x18001ed22  push    rbp
0x18001ed23  push    rsi
0x18001ed24  push    rdi
0x18001ed25  push    r14
0x18001ed27  sub     rsp, 30h
0x18001ed2b  mov     r14, r8
0x18001ed2e  mov     rdi, rdx
0x18001ed31  mov     rbx, rcx
0x18001ed34  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed3b  lea     rbp, WPP_GLOBAL_Control
0x18001ed42  cmp     rcx, rbp
0x18001ed45  jz      short loc_18001ED51
0x18001ed47  test    byte ptr [rcx+1Ch], 2
0x18001ed4b  jnz     loc_18001EEC9
0x18001ed51  mov     esi, 80004003h
0x18001ed56  test    r14, r14
0x18001ed59  jz      loc_18001EDEC
0x18001ed5f  mov     qword ptr [r14], 0
0x18001ed66  mov     esi, 80004002h
0x18001ed6b  mov     rax, [rdi]
0x18001ed6e  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18001ed75  jnz     short loc_18001ED82
0x18001ed77  mov     rax, [rdi+8]
0x18001ed7b  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18001ed82  test    rax, rax
0x18001ed85  jz      short loc_18001EDCC
0x18001ed87  mov     rax, [rdi]
0x18001ed8a  sub     rax, qword ptr cs:IID_IApplicationSyncServices.Data1
0x18001ed91  jnz     short loc_18001ED9E
0x18001ed93  mov     rax, [rdi+8]
0x18001ed97  sub     rax, qword ptr cs:IID_IApplicationSyncServices.Data4
0x18001ed9e  test    rax, rax
0x18001eda1  jz      short loc_18001EDCC
0x18001eda3  mov     rax, [rdi]
0x18001eda6  sub     rax, qword ptr cs:IID_IProviderSyncServices.Data1
0x18001edad  jnz     short loc_18001EDBA
0x18001edaf  mov     rax, [rdi+8]
0x18001edb3  sub     rax, qword ptr cs:IID_IProviderSyncServices.Data4
0x18001edba  test    rax, rax
0x18001edbd  jnz     short loc_18001EE08
0x18001edbf  lea     rax, [rbx+10h]
0x18001edc3  neg     rbx
0x18001edc6  sbb     rbx, rbx
0x18001edc9  and     rbx, rax
0x18001edcc  test    rbx, rbx
0x18001edcf  jz      short loc_18001EDE5
0x18001edd1  mov     [r14], rbx
0x18001edd4  mov     rcx, rbx
0x18001edd7  mov     rax, [rbx]
0x18001edda  mov     rax, [rax+8]
0x18001edde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ede3  xor     esi, esi
0x18001ede5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edec  cmp     rcx, rbp
0x18001edef  jz      short loc_18001EDFB
0x18001edf1  test    byte ptr [rcx+1Ch], 2
0x18001edf5  jnz     loc_18001EF16
0x18001edfb  mov     eax, esi
0x18001edfd  add     rsp, 30h
0x18001ee01  pop     r14
0x18001ee03  pop     rdi
0x18001ee04  pop     rsi
0x18001ee05  pop     rbp
0x18001ee06  pop     rbx
0x18001ee07  retn
0x18001ee08  mov     rax, [rdi]
0x18001ee0b  sub     rax, qword ptr cs:IID_IProviderSyncServices2.Data1
0x18001ee12  jnz     short loc_18001EE1F
0x18001ee14  mov     rax, [rdi+8]
0x18001ee18  sub     rax, qword ptr cs:IID_IProviderSyncServices2.Data4
0x18001ee1f  test    rax, rax
0x18001ee22  jz      short loc_18001EDBF
0x18001ee24  mov     rax, [rdi]
0x18001ee27  sub     rax, qword ptr cs:IID_IProviderFilteredSyncServices.Data1
0x18001ee2e  jnz     short loc_18001EE3B
0x18001ee30  mov     rax, [rdi+8]
0x18001ee34  sub     rax, qword ptr cs:IID_IProviderFilteredSyncServices.Data4
0x18001ee3b  test    rax, rax
0x18001ee3e  jz      loc_18001EEFB
0x18001ee44  mov     rax, [rdi]
0x18001ee47  sub     rax, qword ptr cs:IID_IProviderFilteredSyncServices2.Data1
0x18001ee4e  jnz     short loc_18001EE5B
0x18001ee50  mov     rax, [rdi+8]
0x18001ee54  sub     rax, qword ptr cs:IID_IProviderFilteredSyncServices2.Data4
0x18001ee5b  test    rax, rax
0x18001ee5e  jz      loc_18001EEFB
0x18001ee64  mov     rax, [rdi]
0x18001ee67  sub     rax, qword ptr cs:IID_IProviderCustomFilteredSyncServices.Data1
0x18001ee6e  jnz     short loc_18001EE7B
0x18001ee70  mov     rax, [rdi+8]
0x18001ee74  sub     rax, qword ptr cs:IID_IProviderCustomFilteredSyncServices.Data4
0x18001ee7b  test    rax, rax
0x18001ee7e  jz      loc_18001EF04
0x18001ee84  mov     rax, [rdi]
0x18001ee87  sub     rax, qword ptr cs:IID_IClockVectorServices.Data1
0x18001ee8e  jnz     short loc_18001EE9B
0x18001ee90  mov     rax, [rdi+8]
0x18001ee94  sub     rax, qword ptr cs:IID_IClockVectorServices.Data4
0x18001ee9b  test    rax, rax
0x18001ee9e  jz      short loc_18001EF0D
0x18001eea0  mov     rax, [rdi]
0x18001eea3  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data1
0x18001eeaa  jnz     short loc_18001EEB7
0x18001eeac  mov     rax, [rdi+8]
0x18001eeb0  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data4
0x18001eeb7  test    rax, rax
0x18001eeba  jnz     loc_18001EDE5
0x18001eec0  lea     rax, [rbx+28h]
0x18001eec4  jmp     loc_18001EDC3
0x18001eec9  cmp     byte ptr [rcx+19h], 5
0x18001eecd  jb      loc_18001ED51
0x18001eed3  mov     rcx, [rcx+10h]
0x18001eed7  lea     r9, aCsyncservicesQ; "CSyncServices::QueryInterface"
0x18001eede  mov     edx, 0Ah
0x18001eee3  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18001eeea  call    WPP_SF_s
0x18001eeef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eef6  jmp     loc_18001ED51
0x18001eefb  lea     rax, [rbx+8]
0x18001eeff  jmp     loc_18001EDC3
0x18001ef04  lea     rax, [rbx+18h]
0x18001ef08  jmp     loc_18001EDC3
0x18001ef0d  lea     rax, [rbx+20h]
0x18001ef11  jmp     loc_18001EDC3
0x18001ef16  cmp     byte ptr [rcx+19h], 5
0x18001ef1a  jb      loc_18001EDFB
0x18001ef20  mov     rcx, [rcx+10h]
0x18001ef24  lea     r9, aCsyncservicesQ; "CSyncServices::QueryInterface"
0x18001ef2b  mov     edx, 0Bh
0x18001ef30  mov     [rsp+58h+var_38], esi
0x18001ef34  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18001ef3b  call    WPP_SF_sD
0x18001ef40  jmp     loc_18001EDFB
```
