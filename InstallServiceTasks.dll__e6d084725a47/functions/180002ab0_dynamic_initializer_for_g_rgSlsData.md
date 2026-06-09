# _dynamic_initializer_for__g_rgSlsData__

- ea: `0x180002ab0`
- end: `0x180002bc0`
- name: `_dynamic_initializer_for__g_rgSlsData__`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180003fe4`

## string_xrefs

- `0x180002af2`: `https://displaycatalog.mp.microsoft.com/v7/products?bigIds={productIdsWithCommas}&market={marketCode}&languages={languages}&fieldsTemplate={fieldsTemplate}`
- `0x180002b4c`: `https://purchase.mp.microsoft.com/v7.0/users/{userId}/orders/{orderId}`
- `0x180002b1f`: `https://displaycatalog.mp.microsoft.com/v7.0/products/lookup?alternateId={idType}&value={productId}&market={marketCode}&languages={language}&fieldsTemplate={fieldsTemplate}`
- `0x180002ba6`: `https://storeedgefd.dsx.mp.microsoft.com/v8.0/campaigns?type=install&market={marketCode}&cid={cid}&ocid={ocid}&productId={productId}&skuid={skuid}&callercontext={clientid}&caller=InstallAgent`
- `0x180002b79`: `https://storeedgefd.dsx.mp.microsoft.com/v7.0/oemdiscovery?oemId={oemId}&scmId={scmId}&phoneManufacturerName={phoneManufacturerName}&smBiosManufacturerName={smBiosManufacturerName}&phoneDeviceModel={phoneDeviceModel}&smBiosDm={smBiosDm}`

## pseudocode

```c
void *dynamic_initializer_for__g_rgSlsData__()
{
  g_rgSlsData = (struct _unnamed_type_g_rgSlsData_ near *)L"MDv7ProductDetails";
  memset_0(qword_180063150, 0, sizeof(qword_180063150));
  qword_180064198 = (__int64)L"MDv7BulkProductDetails";
  qword_1800641A0 = (__int64)L"https://displaycatalog.mp.microsoft.com/v7/products?bigIds={productIdsWithCommas}&market={m"
                              "arketCode}&languages={languages}&fieldsTemplate={fieldsTemplate}";
  memset_0(qword_1800641A8, 0, sizeof(qword_1800641A8));
  qword_1800651F0 = (__int64)L"MDv7AlternateIdLookup";
  qword_1800651F8 = (__int64)L"https://displaycatalog.mp.microsoft.com/v7.0/products/lookup?alternateId={idType}&value={pr"
                              "oductId}&market={marketCode}&languages={language}&fieldsTemplate={fieldsTemplate}";
  memset_0(qword_180065200, 0, sizeof(qword_180065200));
  qword_180066248 = (__int64)L"MDv7PurchaseOrder";
  qword_180066250 = (__int64)L"https://purchase.mp.microsoft.com/v7.0/users/{userId}/orders/{orderId}";
  memset_0(qword_180066258, 0, sizeof(qword_180066258));
  qword_1800672A0 = (__int64)L"OemIdentification";
  qword_1800672A8 = (__int64)L"https://storeedgefd.dsx.mp.microsoft.com/v7.0/oemdiscovery?oemId={oemId}&scmId={scmId}&phon"
                              "eManufacturerName={phoneManufacturerName}&smBiosManufacturerName={smBiosManufacturerName}&"
                              "phoneDeviceModel={phoneDeviceModel}&smBiosDm={smBiosDm}";
  memset_0(qword_1800672B0, 0, sizeof(qword_1800672B0));
  qword_1800682F8 = (__int64)L"CampaignServiceUrl";
  qword_180068300 = (__int64)L"https://storeedgefd.dsx.mp.microsoft.com/v8.0/campaigns?type=install&market={marketCode}&ci"
                              "d={cid}&ocid={ocid}&productId={productId}&skuid={skuid}&callercontext={clientid}&caller=InstallAgent";
  return memset_0(qword_180068308, 0, sizeof(qword_180068308));
}

```

## disassembly

```asm
0x180002ab0  push    rbx
0x180002ab2  sub     rsp, 20h
0x180002ab6  mov     rax, cs:off_1800486E0; "MDv7ProductDetails"
0x180002abd  lea     rcx, qword_180063150; void *
0x180002ac4  mov     ebx, 1048h
0x180002ac9  mov     cs:?g_rgSlsData@@3PAU_unnamed_type_g_rgSlsData_@@A, rax; _unnamed_type_g_rgSlsData_ near * g_rgSlsData
0x180002ad0  mov     r8d, ebx; Size
0x180002ad3  xor     edx, edx; Val
0x180002ad5  call    memset_0
0x180002ada  mov     rax, cs:off_1800486E8; "MDv7BulkProductDetails"
0x180002ae1  lea     rcx, qword_1800641A8; void *
0x180002ae8  mov     cs:qword_180064198, rax
0x180002aef  mov     r8d, ebx; Size
0x180002af2  lea     rax, aHttpsDisplayca_0; "https://displaycatalog.mp.microsoft.com"...
0x180002af9  xor     edx, edx; Val
0x180002afb  mov     cs:qword_1800641A0, rax
0x180002b02  call    memset_0
0x180002b07  mov     rax, cs:off_1800486F0; "MDv7AlternateIdLookup"
0x180002b0e  lea     rcx, qword_180065200; void *
0x180002b15  mov     cs:qword_1800651F0, rax
0x180002b1c  mov     r8d, ebx; Size
0x180002b1f  lea     rax, aHttpsDisplayca_1; "https://displaycatalog.mp.microsoft.com"...
0x180002b26  xor     edx, edx; Val
0x180002b28  mov     cs:qword_1800651F8, rax
0x180002b2f  call    memset_0
0x180002b34  mov     rax, cs:off_1800486F8; "MDv7PurchaseOrder"
0x180002b3b  lea     rcx, qword_180066258; void *
0x180002b42  mov     cs:qword_180066248, rax
0x180002b49  mov     r8d, ebx; Size
0x180002b4c  lea     rax, aHttpsPurchaseM; "https://purchase.mp.microsoft.com/v7.0/"...
0x180002b53  xor     edx, edx; Val
0x180002b55  mov     cs:qword_180066250, rax
0x180002b5c  call    memset_0
0x180002b61  mov     rax, cs:off_180048700; "OemIdentification"
0x180002b68  lea     rcx, qword_1800672B0; void *
0x180002b6f  mov     cs:qword_1800672A0, rax
0x180002b76  mov     r8d, ebx; Size
0x180002b79  lea     rax, aHttpsStoreedge; "https://storeedgefd.dsx.mp.microsoft.co"...
0x180002b80  xor     edx, edx; Val
0x180002b82  mov     cs:qword_1800672A8, rax
0x180002b89  call    memset_0
0x180002b8e  mov     rax, cs:off_180048708; "CampaignServiceUrl"
0x180002b95  lea     rcx, qword_180068308; void *
0x180002b9c  mov     cs:qword_1800682F8, rax
0x180002ba3  mov     r8d, ebx; Size
0x180002ba6  lea     rax, aHttpsStoreedge_0; "https://storeedgefd.dsx.mp.microsoft.co"...
0x180002bad  xor     edx, edx; Val
0x180002baf  mov     cs:qword_180068300, rax
0x180002bb6  add     rsp, 20h
0x180002bba  pop     rbx
0x180002bbb  jmp     memset_0
```
