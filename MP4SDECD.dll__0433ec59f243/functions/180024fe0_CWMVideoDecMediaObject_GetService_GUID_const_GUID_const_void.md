# CWMVideoDecMediaObject::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x180024fe0`
- end: `0x180025081`
- name: `?GetService@CWMVideoDecMediaObject@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `161`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180024fe0`
- `0x180025268`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::GetService(
        CWMVideoDecMediaObject *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v6; // r10
  __int64 v7; // rcx
  char *v8; // rax
  unsigned __int64 v9; // rdx
  __int64 v11; // rax
  __int64 v12; // rax

  v6 = *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1 == *(_QWORD *)&a2->Data1 )
    v6 = *(_QWORD *)MF_RATE_CONTROL_SERVICE.Data4 - *(_QWORD *)a2->Data4;
  if ( !v6 )
  {
    v7 = *(_QWORD *)&IID_IMFRateControl.Data1 - *(_QWORD *)&a3->Data1;
    if ( *(_QWORD *)&IID_IMFRateControl.Data1 == *(_QWORD *)&a3->Data1 )
      v7 = *(_QWORD *)IID_IMFRateControl.Data4 - *(_QWORD *)a3->Data4;
    if ( !v7 )
    {
      v8 = (char *)this - 480;
      v9 = (unsigned __int64)this + 8;
      return CodecDSPGetInterface(v9 & -(__int64)(v8 != 0), a4);
    }
  }
  v11 = *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1 - *(_QWORD *)&a2->Data1;
  if ( !v11 )
    v11 = *(_QWORD *)MF_RATE_CONTROL_SERVICE.Data4 - *(_QWORD *)a2->Data4;
  if ( !v11 )
  {
    v12 = *(_QWORD *)&IID_IMFRateSupport.Data1 - *(_QWORD *)&a3->Data1;
    if ( *(_QWORD *)&IID_IMFRateSupport.Data1 == *(_QWORD *)&a3->Data1 )
      v12 = *(_QWORD *)IID_IMFRateSupport.Data4 - *(_QWORD *)a3->Data4;
    if ( !v12 )
    {
      v8 = (char *)this - 480;
      v9 = (unsigned __int64)this + 16;
      return CodecDSPGetInterface(v9 & -(__int64)(v8 != 0), a4);
    }
  }
  return 3222091450LL;
}

```

## disassembly

```asm
0x180024fe0  mov     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data1
0x180024fe7  mov     r11, rdx
0x180024fea  mov     r10, rax
0x180024fed  mov     rdx, rcx
0x180024ff0  sub     r10, [r11]
0x180024ff3  jnz     short loc_180025000
0x180024ff5  mov     r10, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data4
0x180024ffc  sub     r10, [r11+8]
0x180025000  test    r10, r10
0x180025003  jnz     short loc_18002503D
0x180025005  mov     rcx, qword ptr cs:IID_IMFRateControl.Data1
0x18002500c  sub     rcx, [r8]
0x18002500f  jnz     short loc_18002501C
0x180025011  mov     rcx, qword ptr cs:IID_IMFRateControl.Data4
0x180025018  sub     rcx, [r8+8]
0x18002501c  test    rcx, rcx
0x18002501f  jnz     short loc_18002503D
0x180025021  lea     rax, [rdx-1E0h]
0x180025028  add     rdx, 8
0x18002502c  neg     rax
0x18002502f  sbb     rcx, rcx
0x180025032  and     rcx, rdx
0x180025035  mov     rdx, r9
0x180025038  jmp     CodecDSPGetInterface
0x18002503d  sub     rax, [r11]
0x180025040  jnz     short loc_18002504D
0x180025042  mov     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data4
0x180025049  sub     rax, [r11+8]
0x18002504d  test    rax, rax
0x180025050  jnz     short loc_18002507B
0x180025052  mov     rax, qword ptr cs:IID_IMFRateSupport.Data1
0x180025059  sub     rax, [r8]
0x18002505c  jnz     short loc_180025069
0x18002505e  mov     rax, qword ptr cs:IID_IMFRateSupport.Data4
0x180025065  sub     rax, [r8+8]
0x180025069  test    rax, rax
0x18002506c  jnz     short loc_18002507B
0x18002506e  lea     rax, [rdx-1E0h]
0x180025075  add     rdx, 10h
0x180025079  jmp     short loc_18002502C
0x18002507b  mov     eax, 0C00D36BAh
0x180025080  retn
```
