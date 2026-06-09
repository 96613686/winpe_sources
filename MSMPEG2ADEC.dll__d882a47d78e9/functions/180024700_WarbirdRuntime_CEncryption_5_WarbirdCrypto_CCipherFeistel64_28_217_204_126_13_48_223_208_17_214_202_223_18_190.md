# WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Encrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6 *)

- ea: `0x180024700`
- end: `0x180024781`
- name: `?Encrypt@?$CEncryption@$04V?$CCipherFeistel64@$0BM@$0NJ@$0MM@$0HO@$0N@$0DA@$0NP@$0NA@$0BB@$0NG@$0MK@$0NP@$0BC@$0LO@$0KF@$0IJ@$07$0KN@$0NK@$0PM@$0L@$0DO@$0KH@$0LN@$0O@$0FN@$0CA@$0CD@$0BO@$0FL@$0JF@$0CD@$01$0OH@$0EK@$0LG@$0BI@$0ON@$0HO@$0KJ@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$00$01$0CAFEBNIPCLCBHOGE@@2@UENCRYPTED_SEGMENT_DATA_CONST_6@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_6@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_6@2@@Z`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010cf0`

## callees

- `0x180022f00`
- `0x180024700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024768`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024768`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024721`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024721`

## pseudocode

```c
__int64 WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::Encrypt()
{
  unsigned int v1; // ebx

  if ( (WarbirdRuntime::g_EncryptedSegmentConstData_65 & 1) == 0 )
    return 0;
  EnterCriticalSection(&WarbirdRuntime::g_encryptionLock);
  if ( WarbirdRuntime::g_EncryptedSegmentReadWriteData_65 == 1 )
  {
    v1 = WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::DoCrypt();
    WarbirdRuntime::g_EncryptedSegmentReadWriteData_65 = 0;
  }
  else
  {
    v1 = 0;
    if ( (unsigned int)(WarbirdRuntime::g_EncryptedSegmentReadWriteData_65 - 1) <= 0xFFFFFFFD )
      --WarbirdRuntime::g_EncryptedSegmentReadWriteData_65;
  }
  LeaveCriticalSection(&WarbirdRuntime::g_encryptionLock);
  return v1;
}

```

## disassembly

```asm
0x180024700  sub     rsp, 28h
0x180024704  test    cs:?g_EncryptedSegmentConstData_65@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_6@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6 WarbirdRuntime::g_EncryptedSegmentConstData_65
0x18002470b  jnz     short loc_180024715
0x18002470d  xor     eax, eax
0x18002470f  add     rsp, 28h
0x180024713  retn
0x180024715  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x18002471c  mov     [rsp+28h+var_8], rbx
0x180024721  call    cs:__imp_EnterCriticalSection
0x180024728  nop     dword ptr [rax+rax+00h]
0x18002472d  mov     ecx, cs:?g_EncryptedSegmentReadWriteData_65@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6 WarbirdRuntime::g_EncryptedSegmentReadWriteData_65
0x180024733  cmp     ecx, 1
0x180024736  jnz     short loc_18002474E
0x180024738  mov     r8d, ecx
0x18002473b  call    ?DoCrypt@?$CEncryption@$04V?$CCipherFeistel64@$0BM@$0NJ@$0MM@$0HO@$0N@$0DA@$0NP@$0NA@$0BB@$0NG@$0MK@$0NP@$0BC@$0LO@$0KF@$0IJ@$07$0KN@$0NK@$0PM@$0L@$0DO@$0KH@$0LN@$0O@$0FN@$0CA@$0CD@$0BO@$0FL@$0JF@$0CD@$01$0OH@$0EK@$0LG@$0BI@$0ON@$0HO@$0KJ@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$00$01$0CAFEBNIPCLCBHOGE@@2@UENCRYPTED_SEGMENT_DATA_CONST_6@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_6@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_6@2@H@Z; WarbirdRuntime::CEncryption<5,WarbirdCrypto::CCipherFeistel64<28,217,204,126,13,48,223,208,17,214,202,223,18,190,165,137,8,173,218,252,11,62,167,189,14,93,32,35,30,91,149,35,2,231,74,182,24,237,126,169>,WarbirdCrypto::CHashFunctionSCP<1,1,2,2329519407998533220>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_6 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6 *,int)
0x180024740  mov     ebx, eax
0x180024742  mov     cs:?g_EncryptedSegmentReadWriteData_65@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@1@A, 0; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6 WarbirdRuntime::g_EncryptedSegmentReadWriteData_65
0x18002474c  jmp     short loc_180024761
0x18002474e  xor     ebx, ebx
0x180024750  lea     eax, [rcx-1]
0x180024753  cmp     eax, 0FFFFFFFDh
0x180024756  ja      short loc_180024761
0x180024758  lea     eax, [rcx-1]
0x18002475b  mov     cs:?g_EncryptedSegmentReadWriteData_65@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_6@1@A, eax; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_6 WarbirdRuntime::g_EncryptedSegmentReadWriteData_65
0x180024761  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180024768  call    cs:__imp_LeaveCriticalSection
0x18002476f  nop     dword ptr [rax+rax+00h]
0x180024774  mov     eax, ebx
0x180024776  mov     rbx, [rsp+28h+var_8]
0x18002477b  add     rsp, 28h
0x18002477f  retn
```
