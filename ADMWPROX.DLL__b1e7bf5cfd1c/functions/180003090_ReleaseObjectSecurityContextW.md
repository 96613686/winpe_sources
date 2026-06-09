# ReleaseObjectSecurityContextW

- ea: `0x180003090`
- end: `0x180003133`
- name: `ReleaseObjectSecurityContextW`
- size: `163`
- prototype: `void __fastcall(struct IUnknown *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800025b0`

## callees

- `0x180001124`
- `0x180003090`
- `0x18000313c`
- `0x1800031f4`
- `0x180003dd8`
- `0x180003e3c`

## pseudocode

```c
void __fastcall ReleaseObjectSecurityContextW(struct IUnknown *a1)
{
  volatile signed __int32 *v2; // rax
  volatile signed __int32 *v3; // rbx
  volatile signed __int32 *v4; // rax

  v2 = (volatile signed __int32 *)ADM_SECURE_DATA::FindAndReferenceServerSecureData(a1, 0);
  v3 = v2;
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 6, 0xFFFFFFFF) == 1 )
    {
      ADM_SECURE_DATA::~ADM_SECURE_DATA((ADM_SECURE_DATA *)v2);
      operator delete((void *)v3);
    }
    if ( !_InterlockedDecrement(v3 + 6) )
    {
      ADM_SECURE_DATA::~ADM_SECURE_DATA((ADM_SECURE_DATA *)v3);
LABEL_11:
      operator delete((void *)v3);
    }
  }
  else
  {
    v4 = (volatile signed __int32 *)ADM_GUID_MAP::FindAndReferenceGuidMap(a1);
    v3 = v4;
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd(v4 + 6, 0xFFFFFFFF) == 1 )
      {
        ADM_GUID_MAP::~ADM_GUID_MAP((ADM_GUID_MAP *)v4);
        operator delete((void *)v3);
      }
      if ( !_InterlockedDecrement(v3 + 6) )
      {
        ADM_GUID_MAP::~ADM_GUID_MAP((ADM_GUID_MAP *)v3);
        goto LABEL_11;
      }
    }
  }
}

```

## disassembly

```asm
0x180003090  mov     [rsp+arg_0], rbx
0x180003095  push    rdi
0x180003096  sub     rsp, 20h
0x18000309a  xor     edx, edx; int
0x18000309c  mov     rdi, rcx
0x18000309f  call    ?FindAndReferenceServerSecureData@ADM_SECURE_DATA@@SAPEAV1@PEAUIUnknown@@H@Z; ADM_SECURE_DATA::FindAndReferenceServerSecureData(IUnknown *,int)
0x1800030a4  mov     rbx, rax
0x1800030a7  test    rax, rax
0x1800030aa  jz      short loc_1800030DF
0x1800030ac  or      edi, 0FFFFFFFFh
0x1800030af  mov     ecx, edi
0x1800030b1  lock xadd [rax+18h], ecx
0x1800030b6  add     ecx, edi
0x1800030b8  jnz     short loc_1800030CA
0x1800030ba  mov     rcx, rax; this
0x1800030bd  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x1800030c2  mov     rcx, rbx; Block
0x1800030c5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800030ca  mov     eax, edi
0x1800030cc  lock xadd [rbx+18h], eax
0x1800030d1  add     eax, edi
0x1800030d3  jnz     short loc_180003128
0x1800030d5  mov     rcx, rbx; this
0x1800030d8  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x1800030dd  jmp     short loc_180003120
0x1800030df  mov     rcx, rdi; struct IUnknown *
0x1800030e2  call    ?FindAndReferenceGuidMap@ADM_GUID_MAP@@SAPEAV1@PEAUIUnknown@@@Z; ADM_GUID_MAP::FindAndReferenceGuidMap(IUnknown *)
0x1800030e7  mov     rbx, rax
0x1800030ea  test    rax, rax
0x1800030ed  jz      short loc_180003128
0x1800030ef  or      edi, 0FFFFFFFFh
0x1800030f2  mov     ecx, edi
0x1800030f4  lock xadd [rax+18h], ecx
0x1800030f9  add     ecx, edi
0x1800030fb  jnz     short loc_18000310D
0x1800030fd  mov     rcx, rax; this
0x180003100  call    ??1ADM_GUID_MAP@@QEAA@XZ; ADM_GUID_MAP::~ADM_GUID_MAP(void)
0x180003105  mov     rcx, rbx; Block
0x180003108  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000310d  mov     eax, edi
0x18000310f  lock xadd [rbx+18h], eax
0x180003114  add     eax, edi
0x180003116  jnz     short loc_180003128
0x180003118  mov     rcx, rbx; this
0x18000311b  call    ??1ADM_GUID_MAP@@QEAA@XZ; ADM_GUID_MAP::~ADM_GUID_MAP(void)
0x180003120  mov     rcx, rbx; Block
0x180003123  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003128  mov     rbx, [rsp+28h+arg_0]
0x18000312d  add     rsp, 20h
0x180003131  pop     rdi
0x180003132  retn
```
